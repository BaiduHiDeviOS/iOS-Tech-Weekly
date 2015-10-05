# iOS技术周报分类

### 周报博客地址：[点我](http://baiduhidevios.github.io/)



## Swift

名称  |  简介
---- | ----
[What's New in Swift 2.0](https://developer.apple.com/videos/wwdc/2015/?id=106) | WWDC 2015 关于Swift 2.0 新特性的介绍Session, 可以通过此视频快速了解Swift 2.0的主要变化。
[@UIApplicationMain](http://swifter.tips/uiapplicationmain/) | 最近学Swift，新建项目以后发现找不到以前的main函数了。就查了一下怎么回事，详见此文。
[@UIApplicationMain](http://swifter.tips/uiapplicationmain/) | 最近学Swift，新建项目以后发现找不到以前的main函数了。就查了一下怎么回事，详见此文。
[The Swift Programming Language](http://wiki.jikexueyuan.com/project/swift/) | Swift 官方文档中文翻译。
[Thinking in Swift, Part 1: Saving ponies](http://alisoftware.github.io/swift/2015/09/06/thinking-in-swift-1/) | 这篇文章对比oc和Swift， 来帮助读者更快适应Swift的思考方式。
[Thinking in Swift, Part 2: map those arrays](http://alisoftware.github.io/swift/2015/09/20/thinking-in-swift-2/) | 这篇文章对比oc和Swift， 来帮助读者更快适应Swift的思考方式。
[Enums as constants](http://alisoftware.github.io/swift/enum/constants/2015/07/19/enums-as-constants/) | 本文介绍了很多Swift中enum的使用场景，很值得学习。
[Swift 模式识别详解](http://appventure.me/2015/08/20/swift-pattern-matching-in-detail/) | 详细解读如何使用Swift的模式识别
[Swift 2.0 如何写单例](http://krakendev.io/blog/the-right-way-to-write-a-singleton) | Swift 2.0 单例写法

## Objective-C

名称  |  简介
---- | ----
[Adopting Nullability Annotations](http://www.miqu.me/blog/2015/04/17/adopting-nullability-annotations/) | OC新特性，标记对象是否可以为空，为了更好的适配Swift。
[Adopting Objective-C Generics](http://www.miqu.me/blog/2015/06/09/adopting-objectivec-generics/) | OC新特性，标记集合对象（NSArray, NSDictionary, NSSet）中保存对象类型，为了更好的适配Swift。

## 技术实践

文章名称  |  简介
---- | ----
[单元测试框架选型](http://zixun.github.io/blog/2015/04/11/iosdan-yuan-ce-shi-xi-lie-dan-yuan-ce-shi-kuang-jia-xuan-xing/) | 介绍单元测试框架选型，对比几个知名测试框架
[OCMock常见使用方式](http://zixun.github.io/blog/2015/04/16/iosdan-yuan-ce-shi-xi-lie-yi-ocmockchang-jian-shi-yong-fang-shi/) | 介绍CMock常见使用方式
[Singleton如何测试](http://zixun.github.io/blog/2015/04/16/iosdan-yuan-ce-shi-xi-lie-singletonru-he-ce-shi/) | 介绍Singleton如何测试
[单元测试编码规范](http://zixun.github.io/blog/2015/04/16/iosdan-yuan-ce-shi-xi-lie-dan-yuan-ce-shi-bian-ma-gui-fan/) | 介绍单元测试编码规范
[Reducing FOOMs in the Facebook iOS app](https://code.facebook.com/posts/1146930688654547/reducing-fooms-in-the-facebook-ios-app/?utm_campaign=iOS%2BDev%2BWeekly&utm_medium=email&utm_source=iOS_Dev_Weekly_Issue_213) | 这篇文章介绍了Facebook如何减少由于系统内存压力导致的应用Crash。为追踪非应用本身Bug 造成的crash提供了一个思路。
[Faster Photos in Facebook for iOS](https://code.facebook.com/posts/857662304298232/faster-photos-in-facebook-for-ios/) | 这篇文章介绍了Facebook使用Progressive JPEG加快图片加载的优缺点对比。附上一个Progressive image的[开源库](https://github.com/contentful-labs/Concorde)
[On Using SQLite and FMDB Instead of Core Data](https://www.objc.io/issues/4-core-data/SQLite-instead-of-core-data/) | 关于使用Sqlite的一些实践，对我们项目里Sqlite的使用有很多可以借鉴的东西。

## 开源代码
名称 | 推荐理由
------- | -------
[PromiseKit](https://github.com/mxcl/PromiseKit) | Modern development is highly asynchronous: isn’t it about time we had tools that made programming asynchronously powerful, easy and delightful?
[Concorde](https://github.com/contentful-labs/Concorde) | Progressive JPEG 图片加载的三方库。
[ReactiveCocoa](https://github.com/ReactiveCocoa/ReactiveCocoa) | ReactiveCocoa
[Apple 3D Touch Demo](https://developer.apple.com/ios/3d-touch/) | Apple 3D Touch Demo
[MessageDisplayKit](https://github.com/xhzengAIB/MessageDisplayKit) | MessageDisplayKit 模仿微信样式的开源IM
[TeamTalk](https://github.com/mogujie/TeamTalk) | 蘑菇街开源IM
[JSQMessagesViewController](https://github.com/jessesquires/JSQMessagesViewController) | 开源聊天界面组件
[iOS-9-Sampler](https://github.com/shu223/iOS-9-Sampler) | Code examples for the new features of iOS 9.
[React Native](http://facebook.github.io/react-native/) |Facebook的开源库，使用 React.js 开发原生应用。
[FCModel](https://github.com/marcoarment/FCModel) |依据[On Using SQLite and FMDB Instead of Core Data](https://www.objc.io/issues/4-core-data/SQLite-instead-of-core-data/)做了实现。
[ClassyLiveLayout](https://github.com/olegam/ClassyLiveLayout) | Use Classy stylesheets together with Masonry to tweak AutoLayout constants live when debugging in the simulator.
[SnapKit](https://github.com/SnapKit/SnapKit) | SnapKit is a DSL to make Auto Layout easy on both iOS and OS X.
[Hacking With Swift](https://github.com/twostraws/HackingWithSwift) | Swift 教程，以做小项目学习Swift
[Decodable](https://github.com/Anviking/Decodable) | Swift 解析JSON, Chris Lattner(LLVM 作者) 推荐

## 博客

博客地址 | 博主信息
------- | -------
[OneV's Den](http://onevcat.com/#blog) | 王巍(喵神), 现居日本, 就职于 LINE, 知名 iOS 开发者, 写的文章大多深入浅出, 内容广泛, 目前在维护的 [Swifter](http://swifter.tips) 也值得收藏
[唐巧的技术博客](http://blog.devtang.com) | 唐巧, 国内知名 iOS 开发者, 现就职于猿题库, 博客推出的 iOS 移动开发周报很受欢迎, 更新频繁
[txx's blog](http://blog.txx.im) | 90 后 iOS 开发者, 人称虾神, 文章内容讲解大多浅白易懂, 很值得看
[破船之家](http://beyondvincent.com) | 博主也是 iOS 大神一个, 经常更新一些 iOS 教程, 文章的质量都很高, 非常值得看
[NSHipster](http://nshipster.cn) | NSHipster 的中文网站, 主要对 NSHipster 的英文网站进行翻译, 博文出自 Mattt 大神之手, 文章大都写得很深入, 详细, 每周一更
[Limboy 无网不剩](http://blog.leezhong.com) | 李忠, 知乎前员工, 目前在负责花瓣 iOS 开发, 不少文章里面有介绍博主个人的学习方法, 让读者在学到技术的同时也掌握学习的技巧
[iOS技术周报](http://weekly.ios-wiki.com/history) | 吴发伟, 天猫资深软件开发工程师, iOS 技术周报每周一更, 推送一些 iOS 技巧, 代码库, 设计等资讯.
[iWangKe.me](http://www.iwangke.me) | 王轲, IndieBros Studio 创始人, 优秀的 iOS 开发工程师, 写的文章深入浅出, 很多问题分析透彻, 非常有条理性
[叶孤城](http://www.jianshu.com/p/99e8b3f6f377) | 叶孤城, 优秀 iOS 开发工程师, 发表的文章都有很多干货, 对源码解析类文章写得浅显易懂, 并时常总结一些 iOS 开发技巧, 值得一读
[Kevin Blog](http://zhowkev.in) | 周楷雯, 秒视创始人, 知名 iOS 工程师, 做出了 [PNChart](https://github.com/kevinzhow/PNChart) 和 [Waver](https://github.com/kevinzhow/Waver) 这样的好项目, 在博客中也有谈到具体的实现过程
[IMTX](http://imtx.me) | 图拉鼎, 知名 Apple 平台开发者, 曾经的 Ubuntu 平台开发者, 文章有不少干货, 大多讲解技术实现和学习经验
[Facebook iOS技术博客](https://code.facebook.com/ios/) | Facebook 在iOS上的一些优秀实践，很多值得我们学习，希望大家也多多关注。

## 文章

标题  | 内容简介
---- | -----
[iOS应用架构谈](http://casatwy.com/iosying-yong-jia-gou-tan-kai-pian.html) | 对iOS应用架构的深入探讨文章，推荐阅读。
[Automatically Formatting Your Objective-C](http://tonyarnold.com/2014/05/31/autoformatting-your-code.html) | 自动格式化代码工具[ClangFormat-Xcode](https://github.com/travisjeffery/ClangFormat-Xcode/)使用。
[CALayer Animation实践（一）：让应用灵动起来！](http://www.csdn.net/article/2015-09-07/2825633/1) | CALayer 动画实践（一）
[CALayer动画实践（二）：CAReplicatorLayer的用法](http://www.csdn.net/article/2015-09-09/2825659/2) | CALayer 动画实践（二）
[iOS 7 - 9新特性总结](http://anyuan.me/ios-7-9-xin-te-xing-zong-jie/) | 总结iOS7-9开发者应该关注的变化。
[代码整洁之所以重要的七个理由](http://blog.jobbole.com/61312/) | 为什么代码整洁是如此重要
[技术债务：究竟让你付出了多大代价？](http://blog.jobbole.com/25137/) | 技术债务：究竟让你付出了多大代价？
[Enemy of the State](https://github.com/jspahrsummers/enemy-of-the-state) | 主要是讲程序设计中`state`的坏处，以及用`stateless`编程的好处。这也是近些年来`Functional Programming`重新流行起来的很重要的原因之一。BTW，推荐这个Slides也是为了安利`ReactiveCocoa`：），可以大幅度的减少iOS开发中的`state`。
[The introduction to Reactive Programming you've been missing](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754) | 虽然是针对`JavaScript`的`Rx`库的，但是对`Reactive Programming`思想描述的非常清晰明了。
[A FIRST LOOK AT REACTIVECOCOA 3.0](http://blog.scottlogic.com/2015/04/24/first-look-reactive-cocoa-3.html) | `ReactiveCocoa` 3.0的API入门文章
[REACTIVECOCOA 3.0 - SIGNAL PRODUCERS AND API CLARITY](http://blog.scottlogic.com/2015/04/28/reactive-cocoa-3-continued.html) | `ReactiveCocoa` 3.0的API入门文章
[CocoaPods的一些略为高级一丁点的使用](http://supermao.cn/cocoapodsde-xie-lue-wei-gao-ji-ding-dian-de-shi-yong/) | CocoaPods的一些略为高级一丁点的使用
[iOS9适配系列教程](https://github.com/ChenYilong/iOS9AdaptationTips) | iOS9适配系列教程
[iOS 9 开发高级技巧 - 通过 12 个团队所提供的技巧来快速适配 iOS 9](https://realm.io/cn/news/tips-for-ios-9-development/) | iOS 9 开发高级技巧 - 通过 12 个团队所提供的技巧来快速适配 iOS 9
[SwiftGG](http://swift.gg/) | 翻译的Swift国外优秀技术博客
## 工具/插件

工具/插件  |  简介
---- | ----
[Carthage](https://github.com/Carthage/Carthage) | 新的依赖管理工具 Carthage，和Cocoapods相比，Carthage是非侵入式的，不会修改xcode工程文件，只是帮助build出来frameworks。更灵活更干净。
[LANTERN](https://getlantern.org/) | 科学上网神器，速度快，稳定。
[XcodeColors](https://github.com/robbiehanson/XcodeColors) | 使 Xcode 调试控制台色彩更丰富
[ClangFormat-Xcode](https://github.com/travisjeffery/ClangFormat-Xcode/) | 代码格式化工具





# FAQ
## 0. Why?
* 把平时组内同学发现的好的技术文章，资讯，开源库发布在这里，让其他同学也能看到。
* 我们坚信技术1+1 远远 大于2.

## 1. When?
* 争取以每周为单位更新 ：>

## 2. Who?
* Hi iOS组内同学提供周报线索。

## 3. What？
* 内容包括但不限于文章，资讯，优秀三方开源库，我们自己整理开源的库。*并注明出处！* 

## 4. How？
* 大家投稿可以直接编辑Next-Weekly-Report.md 文件， 每周发布前，会对大家的投稿进行整理，发布。
