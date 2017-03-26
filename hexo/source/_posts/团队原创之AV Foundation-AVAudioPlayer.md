layout: learning
title: 团队原创之AV Foundation-AVAudioPlayer
date: 2017-03-26 12:26:34
tags:
---

转自[東引瓯越](http://sunyazhou.com/) 技术博客


开篇
--
最近在学习`AV Foundation` 试图把学习内容记录下来 并参考一些博客文章
本期的内容是`AVAudioPlayer`


音频知识基础  
--

> 音频文件的生成过程是将声音信息__采样__、__量化__和__编码__产生的数字信号的过程，__人耳所能听到的声音，最低的频率是从20Hz起一直到最高频率20KHZ__，因此音频文件格式的最大带宽是20KHZ。根据[奈奎斯特](https://zh.wikipedia.org/wiki/%E5%A5%88%E5%A5%8E%E6%96%AF%E7%89%B9%E9%A2%91%E7%8E%87)的理论，只有采样频率高于声音信号最高频率的两倍时，才能把数字信号表示的声音还原成为原来的声音，所以音频文件的采样率一般在__40~50KHZ__，比如最常见的CD音质采样率__44.1KHZ__。 (所以一般大家都觉得CD音质是最好的.) 对声音进行采样、量化过程被称为[脉冲编码调制](https://zh.wikipedia.org/wiki/%E8%84%88%E8%A1%9D%E7%B7%A8%E8%99%9F%E8%AA%BF%E8%AE%8A)（Pulse Code Modulation），简称PCM。PCM数据是最原始的音频数据完全无损，所以PCM数据虽然音质优秀但体积庞大，为了解决这个问题先后诞生了一系列的音频格式，这些音频格式运用不同的方法对音频数据进行压缩，其中有无损压缩（ALAC、APE、FLAC）和有损压缩（MP3、AAC、OGG、WMA）两种 来源:[iOS音频播放 (一)：概述](http://msching.github.io/blog/2014/07/07/audio-in-ios/) by [码农人生](http://msching.github.io/)

--

我觉得程寅大牛的处理音频说的很明白
大神列出一个经典的音频播放流程（以MP3为例）

1. 读取MP3文件
2. 解析采样率、码率、时长等信息，分离MP3中的音频帧
3. 对分离出来的音频帧解码得到PCM数据
4. 对PCM数据进行音效处理（均衡器、混响器等，非必须）
5. 把PCM数据解码成音频信号
6. 把音频信号交给硬件播放
7. 重复1-6步直到播放完成

在iOS系统中apple对上述的流程进行了封装并提供了不同层次的接口 
![](https://developer.apple.com/library/content/documentation/MusicAudio/Conceptual/CoreAudioOverview/Art/core_audio_layers_2x.png)  
> 这是CoreAudio的接口层次  

下面对其中的中高层接口进行功能说明：

* Audio File Services：读写音频数据，可以完成播放流程中的第2步；
* Audio File Stream Services：对音频进行解码，可以完成播放流程中的第2步；
* Audio Converter services：音频数据转换，可以完成播放流程中的第3步；
* Audio Processing Graph Services：音效处理模块，可以完成播放流程中的第4步；
* Audio Unit Services：播放音频数据：可以完成播放流程中的第5步、第6步；
* Extended Audio File Services：Audio File Services和Audio   
* Converter services的结合体；
* AVAudioPlayer/AVPlayer(AVFoundation)：高级接口，可以完成整个音频播放的过程（包括本地文件和网络流播放，第4步除外）；
* Audio Queue Services：高级接口，可以进行录音和播放，可以完成播放流程中的第3、5、6步；
* OpenAL：用于游戏音频播放，暂不讨论

可以看到apple提供的接口类型非常丰富，可以满足各种类别类需求：  

* 如果你只是想实现音频的播放，没有其他需求AVFoundation会很好的满足你的需求。它的接口使用简单、不用关心其中的细节；

* 如果你的app需要对音频进行流播放并且同时存储，那么AudioFileStreamer加AudioQueue能够帮到你，你可以先把音频数据下载到本地，一边下载一边用NSFileHandler等接口读取本地音频文件并交给AudioFileStreamer或者AudioFile解析分离音频帧，分离出来的音频帧可以送给AudioQueue进行解码和播放。如果是本地文件直接读取文件解析即可。（这两个都是比较直接的做法，这类需求也可以用AVFoundation+本地server的方式实现，AVAudioPlayer会把请求发送给本地server，由本地server转发出去，获取数据后在本地server中存储并转送给AVAudioPlayer。另一个比较trick的做法是先把音频下载到文件中，在下载到一定量的数据后把文件路径给AVAudioPlayer播放，当然这种做法在音频seek后就回有问题了。）
* 如果你正在开发一个专业的音乐播放软件，需要对音频施加音效（均衡器、混响器），那么除了数据的读取和解析以外还需要用到AudioConverter来把音频数据转换成PCM数据，再由AudioUnit+AUGraph来进行音效处理和播放（但目前多数带音效的app都是自己开发音效模块来坐PCM数据的处理，这部分功能自行开发在自定义性和扩展性上会比较强一些。PCM数据通过音效器处理完成后就可以使用AudioUnit播放了，当然AudioQueue也支持直接使对PCM数据进行播放。）。下图描述的就是使用AudioFile + AudioConverter + AudioUnit进行音频播放的流程

![](http://msching.github.io/images/iOS-audio/audioUnitPlay.jpg)

以上内容均转自[码农人生](http://msching.github.io/blog/2014/07/07/audio-in-ios/) 希望大神不要介意 如果有问题 我可立即清除




使用`AVAudioPlayer `之前对AudioSession简介
--
> `AVAudioSession`负责管理音频会话 它是个单例 在应用程序和操作系统之间负责中间人的角色 [AudioSession参考](http://msching.github.io/blog/2014/07/08/audio-in-ios-2/) 

`AVAudioSession`主要功能包括以下几点：

* app是如何使用的音频服务 播放 还是录制 之类的
* 控制协调app输入输出设备（比如 麦克风，耳机、手机外放比如蓝牙连接一个外置音响 或airplay）
* 协调你的app的音频播放和系统以及其他app行为（例如有电话时需要打断，电话结束时需要恢复，按下静音按钮时是否歌曲也要静音等）

![](https://developer.apple.com/library/content/documentation/Audio/Conceptual/AudioSessionProgrammingGuide/Art/aspg_intro_2x.png)

*注：AVAudioSession iOS6以后使用 以前叫AudioSession__*

如何使用`AVAudioPlayer`
--

在我的博客里面我尽量使用code胜过千言万语
使用`AVAudioPlayer`之前需要在`AppDelegate`里面导入`#import <AVFoundation/AVFoundation.h>`  
并且启动音频会话


``` objc  

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

AVAudioSession *session = [AVAudioSession sharedInstance];
NSError *error;
if (![session setCategory:AVAudioSessionCategoryPlayback error:&error]) {
NSLog(@"Category Error: %@", [error localizedDescription]);
}

if (![session setActive:YES error:&error]) {
NSLog(@"Activation Error: %@", [error localizedDescription]);
}

return YES;
}
```

上边已经介绍了`AVAudioSession`  

这里面说一下`[session setCategory:AVAudioSessionCategoryPlayback error:&error]` 里面的`AVAudioSessionCategoryPlayback`

![音频会话分类](https://raw.githubusercontent.com/sunyazhou13/sunyazhou13.github.io-images/master/Learning%20AV%20Foundation2AVAudioPlayer/AVAudioPlayer_category.png)

这是这几种分类的列表大家可以看下

记得开启后台播放
![](https://raw.githubusercontent.com/sunyazhou13/sunyazhou13.github.io-images/master/Learning%20AV%20Foundation2AVAudioPlayer/MacHi%202017-03-19%2022-43-36.png)  
或者在plist里面修改
![](https://raw.githubusercontent.com/sunyazhou13/sunyazhou13.github.io-images/master/Learning%20AV%20Foundation2AVAudioPlayer/MacHi%202017-03-19%2022-44-05.png)  


下面就是创建音频播放器代码

``` objc

#import "ViewController.h"
#import <Masonry/Masonry.h>

#import "THControlKnob.h"
#import "THPlayButton.h"
#import <AVFoundation/AVFoundation.h>

@interface ViewController ()

//三个控制推子
@property (weak, nonatomic) IBOutlet THOrangeControlKnob *panKnob;
@property (weak, nonatomic) IBOutlet THOrangeControlKnob *volumnKnob;
@property (weak, nonatomic) IBOutlet THGreenControlKnob *rateKnob;
@property (weak, nonatomic) IBOutlet THPlayButton *playButton;

//音乐播放器
@property (nonatomic, strong) AVAudioPlayer *musicPlayer;
@property (nonatomic, getter = isPlaying) BOOL playing; //播放状态

//无关代码
@property (weak, nonatomic) IBOutlet UILabel *LeftRightRoundDec;
@property (weak, nonatomic) IBOutlet UILabel *voiceDec;
@property (weak, nonatomic) IBOutlet UILabel *rateDec;
@property (weak, nonatomic) IBOutlet UILabel *trackDescrption;

@end  

```

> 导入几个第三方控件的类用于音乐播放

![](https://raw.githubusercontent.com/sunyazhou13/sunyazhou13.github.io-images/master/Learning%20AV%20Foundation2AVAudioPlayer/MacHi%202017-03-19%2021-22-43.png)

这上边的三个旋钮就是导入的开源库

下面创建播放器`AVAudioPlayer`  
创建时需要一个`NSURL`代表要播放的文件路径 这里简单从bundle中拖了一首歌进去了


``` objc

#pragma mark -
#pragma mark - 创建AVAudioPlayer与播放状态控制
/**
创建音乐播放器

@param fileName 文件名
@param fileExtension 文件扩展名
@return 播放器实例
*/
- (AVAudioPlayer *)createPlayForFile:(NSString *)fileName
withExtension:(NSString *)fileExtension{
NSURL *url = [[NSBundle mainBundle] URLForResource:fileName withExtension:fileExtension];
NSError *error = nil;
AVAudioPlayer *audioPlayer = [[AVAudioPlayer alloc] initWithContentsOfURL:url error:&error];
if (audioPlayer) {
audioPlayer.numberOfLoops = -1; //-1无限循环
audioPlayer.enableRate = YES; //启动倍速控制
[audioPlayer prepareToPlay];
} else {
NSLog(@"Error creating player: %@",[error localizedDescription]);
}
return audioPlayer;
}

```

`numberOfLoops` = -1; 代表本首歌 无限循环 其它常数代表循环次数     
`enableRate` 代表是否启用倍速调节 0.5x 1.0x 2.0x 等倍速 1.0代表正常速度

这里说一下`[audioPlayer prepareToPlay]`
__调用这个函数是为了取得需要的音频硬件并预加载`Audio Queue`的缓冲区.__ 当然也可以不调用这个方法直接调用 `[audioPlayer play]`，但当  __调用`play`方法时也会隐性激活__,调用`prepareToPlay`是为了减少 创建播放器时预设加载和听到声音输出之间的延时 


``` objc

@implementation ViewController

- (instancetype)initWithNibName:(NSString *)nibNameOrNil bundle:(NSBundle *)nibBundleOrNil {
self = [super initWithNibName:nibNameOrNil bundle:nibBundleOrNil];
if (self) {
if (self.musicPlayer == nil) {
self.musicPlayer = [self createPlayForFile:@"384551_1438267683" withExtension:@"mp3"];
}
[self setupNotifications];
}
return self;
}

- (void)awakeFromNib{
[super awakeFromNib];
if (self.musicPlayer == nil) {
self.musicPlayer = [self createPlayForFile:@"384551_1438267683" withExtension:@"mp3"];
}
[self setupNotifications];

}


```

> 在`initWithNibName`或`awakeFromNib`时候调用一下创建播放器的代码  
这个`[self setupNotifications];`后面说  


先添加一些常见的方法封装 比如 __播放、暂停、停止__
``` objc 

- (void)play {
if (self.musicPlayer == nil) { return; }

if (!self.playing) {
NSTimeInterval delayTime = [self.musicPlayer deviceCurrentTime] + 0.01;
[self.musicPlayer playAtTime:delayTime];
self.playing = YES;
}

self.trackDescrption.text = [self.musicPlayer.url absoluteString];
[self configNowPlayingInfoCenter]; //配置后台播放的页面信息
}
- (void)stop {
if (self.musicPlayer == nil) { return; }
if (self.playing) {
[self.musicPlayer stop];
self.musicPlayer.currentTime = 0.0f;
self.playing = NO;
}
}

- (void)pause {
if (self.musicPlayer == nil) { return; }
if (self.playing) {
[self.musicPlayer pause];
self.playing = NO;
}
}

```
这里看到`[self.musicPlayer deviceCurrentTime] + 0.01` 加了 -0.01的延时, 是为了以后大家做播放器的时候 有可能暂停或者歌曲切换时 有可能 向前向后做片段衔接, 也是为了使用 `playAtTime`去播放 指定位置的音乐用于 意外暂停或者播放上次播放的配置信息使用 这里看到我写了一个  
`[self configNowPlayingInfoCenter];`配置后台播放的页面信息
这个主要用于播放音乐在后台时 锁屏显示的屏幕信息  请看下面代码

``` objc
//设置锁屏状态，显示的歌曲信息
-(void)configNowPlayingInfoCenter{
if (NSClassFromString(@"MPNowPlayingInfoCenter")) {
NSMutableDictionary *dict = [[NSMutableDictionary alloc] init];

//歌曲名称
[dict setObject:@"歌曲名称" forKey:MPMediaItemPropertyTitle];

//演唱者
[dict setObject:@"演唱者" forKey:MPMediaItemPropertyArtist];

//专辑名
[dict setObject:@"专辑名" forKey:MPMediaItemPropertyAlbumTitle];

//专辑缩略图
UIImage *image = [UIImage imageNamed:@"sunyazhou"];
MPMediaItemArtwork *artwork = [[MPMediaItemArtwork alloc] initWithImage:image];
[dict setObject:artwork forKey:MPMediaItemPropertyArtwork];

//音乐剩余时长
[dict setObject:@20 forKey:MPMediaItemPropertyPlaybackDuration];

//音乐当前播放时间 在计时器中修改
// [dict setObject:[NSNumber numberWithDouble:100.0] forKey:MPNowPlayingInfoPropertyElapsedPlaybackTime];

//设置锁屏状态下屏幕显示播放音乐信息
[[MPNowPlayingInfoCenter defaultCenter] setNowPlayingInfo:dict];
}
}

```

如果需要在计时器中不断刷新锁屏状态下的播放进度条请写如下代码

``` objc 
//计时器修改进度
- (void)changeProgress:(NSTimer *)sender{
if(self.player){
//当前播放时间
NSMutableDictionary *dict = [NSMutableDictionary dictionaryWithDictionary:[[MPNowPlayingInfoCenter defaultCenter] nowPlayingInfo]];
[dict setObject:[NSNumber numberWithDouble:self.player.currentTime] forKey:MPNowPlayingInfoPropertyElapsedPlaybackTime]; //音乐当前已经过时间
[[MPNowPlayingInfoCenter defaultCenter] setNowPlayingInfo:dict];

}
}
```

> 参考[IOS后台运行 之 后台播放音乐](http://www.iliunian.com/2831.html) 

下面我们来介绍一下
`[self setupNotifications];`注册监听 音频意外中断和耳机拔出时要暂停音乐播放
实现代码如下

``` objc 
/**
播放的通知处理
*/
- (void)setupNotifications {
NSNotificationCenter *nsnc = [NSNotificationCenter defaultCenter];

//添加意外中断音频播放的通知
[nsnc addObserver:self
selector:@selector(handleInterruption:)
name:AVAudioSessionInterruptionNotification
object:[AVAudioSession sharedInstance]];

//添加线路变化通知
[nsnc addObserver:self
selector:@selector(hanldeRouteChange:)
name:AVAudioSessionRouteChangeNotification
object:[AVAudioSession sharedInstance]];
}


```

*注：记得在delloc里面`[[NSNotificationCenter defaultCenter] removeObserver:self]`*


意外中断音频发生的场景 例如 听歌过程中来电话或者 按住home键使用siri 

下面是具体方法实现

``` objc 
/**
音频意外打断处理

@param notification 通知信息
*/
- (void)handleInterruption:(NSNotification *)notification {
NSDictionary *info = notification.userInfo;
AVAudioSessionInterruptionType type = [info[AVAudioSessionInterruptionTypeKey] unsignedIntegerValue];
if (type == AVAudioSessionInterruptionTypeBegan) {
//Handle AVAudioSessionInterruptionTypeBegan
[self pause];
} else {
//Handle AVAudioSessionInterruptionTypeEnded
AVAudioSessionInterruptionOptions options = [info[AVAudioSessionInterruptionTypeKey] unsignedIntegerValue];
NSError *error = nil;
//激活音频会话 允许外接音响
[[AVAudioSession sharedInstance] setCategory:AVAudioSessionCategoryPlayback
withOptions:AVAudioSessionCategoryOptionAllowBluetooth error:nil];
[[AVAudioSession sharedInstance] setActive:YES withOptions:AVAudioSessionSetActiveOptionNotifyOthersOnDeactivation error:&error];
if (options == AVAudioSessionInterruptionOptionShouldResume) {
[self play];
} else {
[self play];
}


self.playButton.selected = YES;

if (error) {
NSLog(@"AVAudioSessionInterruptionOptionShouldResume失败:%@",[error localizedDescription]);
}
}
}



```

先说`handleInterruption`意外情况下中断比如我按住home键使用siri
我会收到意外打断的通知当 type == `AVAudioSessionInterruptionTypeBegan`时 我们停止音乐播放或者暂停.
当type != `AVAudioSessionInterruptionTypeBegan`的时候一定是`AVAudioSessionInterruptionTypeEnded`这个时候`notification.userInfo`里面包含一个`AVAudioSessionInterruptionOptions`值来表明音频会话是否已经重新激活以及是否可以再次播放

__*注:这个地方遇到个坑*__ 当意外中断时候有时音频会话会很不灵敏 后来发现这种情况下需要重新激活会话 如下代码:

``` objc
[[AVAudioSession sharedInstance] setActive:YES withOptions:AVAudioSessionSetActiveOptionNotifyOthersOnDeactivation error:&error];
```
这里`AVAudioSessionSetActiveOptionNotifyOthersOnDeactivation`是为了通知其它应用会话被我激活了 很多播放器开发者很不讲究 每次从来不用这个方法导致每次别人播放完音频 自己都收不到音频重新播放的信息 建议大家以和为贵, 写良心代码.

因为我外接的小米蓝牙音响发现还是不好使 最后又补上了`AVAudioSessionCategoryOptionAllowBluetooth`这个  

__激活音频会话 允许外接音响__

``` objc
[[AVAudioSession sharedInstance] setCategory:AVAudioSessionCategoryPlayback withOptions:AVAudioSessionCategoryOptionAllowBluetooth error:nil];

```

就好使了

下面说一下耳机插拔或者USB麦克风断开 Apple有个什么`Human Interface Guidelines(HIG)`相关定义 意思是说当硬件耳机拔出时建议 暂停播放音乐或者麦克风断开时。就是处于静音状态。是为了保密播放内容不被外界听到,不管苹果啥规定 我们都得照办 否则就得被拒。

``` objc
- (void)hanldeRouteChange:(NSNotification *)notification {
NSDictionary *info = notification.userInfo;
AVAudioSessionRouteChangeReason reason = [info[AVAudioSessionRouteChangeReasonKey] unsignedIntegerValue];
//老设备不可用
if (reason == AVAudioSessionRouteChangeReasonOldDeviceUnavailable) {
AVAudioSessionRouteDescription *previousRoute = info[AVAudioSessionRouteChangePreviousRouteKey];
AVAudioSessionPortDescription *previousOutput = previousRoute.outputs[0];
NSString *portType = previousOutput.portType;
if ([portType isEqualToString:AVAudioSessionPortHeadphones]) {
[self stop];
self.playButton.selected = NO;
}

}

}
```

这需要用`AVAudioSessionRouteChangeReasonKey`取出线路切换的原因`AVAudioSessionRouteChangeReason` 原因有这么多

``` objc 
typedef NS_ENUM(NSUInteger, AVAudioSessionRouteChangeReason)
{
AVAudioSessionRouteChangeReasonUnknown = 0,
AVAudioSessionRouteChangeReasonNewDeviceAvailable = 1,
AVAudioSessionRouteChangeReasonOldDeviceUnavailable = 2,
AVAudioSessionRouteChangeReasonCategoryChange = 3,
AVAudioSessionRouteChangeReasonOverride = 4,
AVAudioSessionRouteChangeReasonWakeFromSleep = 6,
AVAudioSessionRouteChangeReasonNoSuitableRouteForCategory = 7,
AVAudioSessionRouteChangeReasonRouteConfigurationChange NS_ENUM_AVAILABLE_IOS(7_0) = 8
} NS_AVAILABLE_IOS(6_0);

```
我们需要这个`AVAudioSessionRouteChangeReasonOldDeviceUnavailable` 判断是否是旧设备
通过`AVAudioSessionRouteChangePreviousRouteKey`拿出

`AVAudioSessionRouteDescription`描述信息  
`previousRoute` 在通过  
`previousRoute.outputs[0]`拿出`AVAudioSessionPortDescription`

拿出`NSString *portType = previousOutput.portType`

如果`[portType isEqualToString:AVAudioSessionPortHeadphones]`

如果是耳机`AVAudioSessionPortHeadphones`则暂停播放


以上就是中断和线路切换的一些代码逻辑

下面我介绍一些好玩的

![](https://raw.githubusercontent.com/sunyazhou13/sunyazhou13.github.io-images/master/Learning%20AV%20Foundation2AVAudioPlayer/IMG_2090.PNG)

前面说的一些后台设置信息显示的内容就是上图所示 在锁屏的时候显示

但是大家一定很奇怪的是怎么实现接收 __锁屏状态下 点击 上一曲 暂停/播放 下一曲等操作__

需要在AppDelegate里面写上

``` objc
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

AVAudioSession *session = [AVAudioSession sharedInstance];
NSError *error;
if (![session setCategory:AVAudioSessionCategoryPlayback error:&error]) {
NSLog(@"Category Error: %@", [error localizedDescription]);
}

if (![session setActive:YES error:&error]) {
NSLog(@"Activation Error: %@", [error localizedDescription]);
}

[[UIApplication sharedApplication] beginReceivingRemoteControlEvents];
[self becomeFirstResponder];
return YES;
}

```

这`[[UIApplication sharedApplication] beginReceivingRemoteControlEvents];`
行代码 以及调用自己为 `[self becomeFirstResponder];`第一响应者 这样写是为了应用响应音频播放 后台切换或者中断的时候更灵敏.

``` objc 
- (BOOL)canBecomeFirstResponder {
return YES;
}
```

然后 写上如下代码 处理__锁屏状态下 点击 上一曲 暂停/播放 下一曲等操作__

``` objc
- (void)remoteControlReceivedWithEvent:(UIEvent *)event {
if (event.type == UIEventTypeRemoteControl) {
switch (event.subtype) {
case UIEventSubtypeRemoteControlPlay:
NSLog(@"暂停播放");
break;
case UIEventSubtypeRemoteControlPause:

NSLog(@"继续播放");
break;
case UIEventSubtypeRemoteControlNextTrack:
NSLog(@"下一曲");
break;
case UIEventSubtypeRemoteControlPreviousTrack:
NSLog(@"上一曲");
break;
default:
break;
}
}
}

```

剩余逻辑大家自己填充吧我就不介绍了. 

好了AVAudioPlayer就到这吧！有啥疑问大家可以评论留言都能看到或者指正我的错误。我会及时改正.

全文完

__文章的最终[demo](https://github.com/sunyazhou13/AVAudioPlayerDemo)__
