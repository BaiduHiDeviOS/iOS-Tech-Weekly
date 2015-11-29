# iOS技术周报分类

### 周报博客地址：[点我](http://baiduhidevios.github.io/)



## Swift

名称  |  简介
---- | ----
[纯Swift2.0工程CocoaChina+从0到1遇到的坑和解决方案](http://zixun.github.io/blog/2015/10/25/chun-swift2-dot-0gong-cheng-cocoachina-plus-cong-0dao-1yu-dao-de-keng-he-jie-jue-fang-an/)|纯Swift2.0工程CocoaChina+从0到1遇到的坑和解决方案
[Advanced & Practical Enum usage in Swift](http://appventure.me/2015/10/17/advanced-practical-enum-examples/)|Swift中Enum的使用实践
[What's New in Swift 2.0](https://developer.apple.com/videos/wwdc/2015/?id=106) | WWDC 2015 关于Swift 2.0 新特性的介绍Session, 可以通过此视频快速了解Swift 2.0的主要变化。
[@UIApplicationMain](http://swifter.tips/uiapplicationmain/) | 最近学Swift，新建项目以后发现找不到以前的main函数了。就查了一下怎么回事，详见此文。
[The Swift Programming Language](http://wiki.jikexueyuan.com/project/swift/) | Swift 官方文档中文翻译。
[Thinking in Swift, Part 1: Saving ponies](http://alisoftware.github.io/swift/2015/09/06/thinking-in-swift-1/) | 这篇文章对比oc和Swift， 来帮助读者更快适应Swift的思考方式。
[Thinking in Swift, Part 2: map those arrays](http://alisoftware.github.io/swift/2015/09/20/thinking-in-swift-2/) | 这篇文章对比oc和Swift， 来帮助读者更快适应Swift的思考方式。
[Enums as constants](http://alisoftware.github.io/swift/enum/constants/2015/07/19/enums-as-constants/) | 本文介绍了很多Swift中enum的使用场景，很值得学习。
[Swift 模式识别详解](http://appventure.me/2015/08/20/swift-pattern-matching-in-detail/) | 详细解读如何使用Swift的模式识别
[Swift 2.0 如何写单例](http://krakendev.io/blog/the-right-way-to-write-a-singleton) | Swift 2.0 单例写法
[Controlling Complexity in Swift](https://realm.io/news/andy-matuschak-controlling-complexity/) | 使用Swift的Value type来控制程序的复杂度
[An Observable Pattern Implementation in Swift](http://colindrake.me/2015/10/01/an-observable-pattern-implementation-in-swift/) | Swift的观察者模式实现
[When to Use Swift Structs and Classes](https://www.mikeash.com/pyblog/friday-qa-2015-07-17-when-to-use-swift-structs-and-classes.html) | Swift中何时使用Structs和Classes
[Optional Computed Properties in Swift Protocols](http://matthewpalmer.net/blog/2015/08/29/optional-computed-property-swift-protocol-non-objc/) | 声明Optional Computed properties
[Protocol Oriented Programming in the Real World](http://matthewpalmer.net/blog/2015/08/30/protocol-oriented-programming-in-the-real-world/) | Swift Protocol Oriented Programming的使用例子。
[Swift Functors, Applicatives, and Monads in Pictures](http://www.mokacoding.com/blog/functor-applicative-monads-in-pictures/) | 学了点`haskell`，在`swift`中新加的很多语言特性都是从`haskell`那里“抄”来的，比如强大的枚举、`switch`等等。`functor`、`applicative`和`monads`历来是`haskell`学习中相对比较难理解的概念，这篇文章用`swift`简明易懂的做了解释。
| [Advanced NSOperations](https://developer.apple.com/videos/play/wwdc2015-226/) | 对于使用NSOperation提供了一个新颖的使用方案，比较开拓思路，此seesion有[sample code](https://developer.apple.com/sample-code/wwdc/2015/downloads/Advanced-NSOperations.zip)结合观看效果更加
| [Inside Swift](http://www.eswick.com/2014/06/inside-swift/) | Swift的内部机制

## Objective-C

名称  |  简介
---- | ----
[深入理解Objective-C：Category](http://tech.meituan.com/DiveIntoCategory.html) | 来自美团技术团队的优质技术文章，深入讲解了Category
[深入理解Objective-C：方法缓存](http://tech.meituan.com/DiveIntoMethodCache.html) | 来自美团技术团队的优质技术文章， 深入讲解了OC中方法调用缓存的相关知识。
[Objective-C 的现代语法和新特性](http://www.cocoachina.com/cms/wap.php?action=article&id=13924)| Objective-C 的现代语法和新特性
[Adopting Nullability Annotations](http://www.miqu.me/blog/2015/04/17/adopting-nullability-annotations/) | OC新特性，标记对象是否可以为空，为了更好的适配Swift。
[Adopting Objective-C Generics](http://www.miqu.me/blog/2015/06/09/adopting-objectivec-generics/) | OC新特性，标记集合对象（NSArray, NSDictionary, NSSet）中保存对象类型，为了更好的适配Swift。
| [Objective-C vs Swift messages dispatch](http://blog.untitledkingdom.co.uk/obj-c-vs-swift/) | Objective-C和Swift的消息派发机制

## 技术实践

文章名称  |  简介
---- | ----
[AFNetworking 3.0迁移指南](http://www.cocoachina.com/ios/20151022/13831.html)|为了迎合iOS新版本的升级，AFNetworking在3.0版本中删除了基于 NSURLConnection API的所有支持。如果你的项目以前使用过这些API，建议您立即升级到基于NSURLSession的API的AFNetworking的版本。
[iOS开发系列--让你的应用“动”起来](http://www.cnblogs.com/kenshincui/p/3972100.html) | 讲解IOS 动画相关~博主的文笔和排版灰常赞~其系列博文值得一读
[优化Facebook iOS app启动时间](https://code.facebook.com/posts/1675399786008080/optimizing-facebook-for-ios-start-time/)|优化Facebook iOS app启动时间
[Lessons learned with 3D Touch](http://engineering.instagram.com/posts/465414923641286/lessons-learned-with-3D-touch) | 详细介绍了3D touch 在instagram app中的应用。
[iOS 保持界面流畅的技巧](http://blog.ibireme.com/2015/11/12/smooth_user_interfaces_for_ios/) | iOS 保持界面流畅的技巧
[AFNetworking2.0源码解析<一>](http://blog.cnbang.net/tech/2320/) | AFNetworking2.0源码解析<一>
[AFNetworking2.0源码解析<二>](http://blog.cnbang.net/tech/2371/) | AFNetworking2.0源码解析<二>
[AFNetworking2.0源码解析<三>](http://blog.cnbang.net/tech/2416/) | AFNetworking2.0源码解析<三>
[iOS 处理图片的一些小 Tip](http://blog.ibireme.com/2015/11/02/ios_image_tips/) | iOS 处理图片的一些小 Tip
[移动端图片格式调研](http://blog.ibireme.com/2015/11/02/mobile_image_benchmark/)| 移动端图片格式调研
[iOS APP安全杂谈之三](http://drops.wooyun.org/papers/9598) | iOS APP安全杂谈之三
[iOS高性能图片架构与设计](http://mp.weixin.qq.com/s?__biz=MzI1MTA1MzM2Nw==&mid=207840007&idx=1&sn=ce09553e5774f5581c696b5e28f0c7e8#rd)| iOS高性能图片架构与设计
[单元测试框架选型](http://zixun.github.io/blog/2015/04/11/iosdan-yuan-ce-shi-xi-lie-dan-yuan-ce-shi-kuang-jia-xuan-xing/) | 介绍单元测试框架选型，对比几个知名测试框架
[OCMock常见使用方式](http://zixun.github.io/blog/2015/04/16/iosdan-yuan-ce-shi-xi-lie-yi-ocmockchang-jian-shi-yong-fang-shi/) | 介绍CMock常见使用方式
[Singleton如何测试](http://zixun.github.io/blog/2015/04/16/iosdan-yuan-ce-shi-xi-lie-singletonru-he-ce-shi/) | 介绍Singleton如何测试
[单元测试编码规范](http://zixun.github.io/blog/2015/04/16/iosdan-yuan-ce-shi-xi-lie-dan-yuan-ce-shi-bian-ma-gui-fan/) | 介绍单元测试编码规范
[Reducing FOOMs in the Facebook iOS app](https://code.facebook.com/posts/1146930688654547/reducing-fooms-in-the-facebook-ios-app/?utm_campaign=iOS%2BDev%2BWeekly&utm_medium=email&utm_source=iOS_Dev_Weekly_Issue_213) | 这篇文章介绍了Facebook如何减少由于系统内存压力导致的应用Crash。为追踪非应用本身Bug 造成的crash提供了一个思路。
[Faster Photos in Facebook for iOS](https://code.facebook.com/posts/857662304298232/faster-photos-in-facebook-for-ios/) | 这篇文章介绍了Facebook使用Progressive JPEG加快图片加载的优缺点对比。附上一个Progressive image的[开源库](https://github.com/contentful-labs/Concorde)
[On Using SQLite and FMDB Instead of Core Data](https://www.objc.io/issues/4-core-data/SQLite-instead-of-core-data/) | 关于使用Sqlite的一些实践，对我们项目里Sqlite的使用有很多可以借鉴的东西。

##应用架构相关
文章名称  |  简介
---- | ----
[跳出面向对象思想(一) 继承](http://casatwy.com/tiao-chu-mian-xiang-dui-xiang-si-xiang-yi-ji-cheng.html)| 跳出面向对象思想(一) 继承
[跳出面向对象思想(二) 多态](http://casatwy.com/tiao-chu-mian-xiang-dui-xiang-si-xiang-er-duo-tai.html)| 跳出面向对象思想(二) 多态
[跳出面向对象思想(三) 封装](http://casatwy.com/tiao-chu-mian-xiang-dui-xiang-si-xiang-san-feng-zhuang.html)| 跳出面向对象思想(三) 封装
[iOS应用架构谈 开篇](http://casatwy.com/iosying-yong-jia-gou-tan-kai-pian.html)| iOS应用架构谈 开篇
[iOS应用架构谈 view层的组织和调用方案](http://casatwy.com/iosying-yong-jia-gou-tan-viewceng-de-zu-zhi-he-diao-yong-fang-an.html)| iOS应用架构谈 view层的组织和调用方案
[iOS应用架构谈 网络层设计方案](http://casatwy.com/iosying-yong-jia-gou-tan-wang-luo-ceng-she-ji-fang-an.html)| iOS应用架构谈 网络层设计方案
[iOS应用架构谈 本地持久化方案及动态部署](http://casatwy.com/iosying-yong-jia-gou-tan-ben-di-chi-jiu-hua-fang-an-ji-dong-tai-bu-shu.html)| iOS应用架构谈 本地持久化方案及动态部署
[Software Architecture Patterns pdf](http://www.oreilly.com/programming/free/files/software-architecture-patterns.pdf)| Software Architecture Patterns |
[构建iOS稳定应用架构时方案选择的思考](http://www.starming.com/index.php?v=index&view=83)| 构建iOS稳定应用架构时方案选择的思考

## 开源代码
名称 | 推荐理由
------- | -------
[SlackTextViewController](https://github.com/slackhq/SlackTextViewController)| A drop-in UIViewController subclass with a growing text input view and other useful messaging features.
[REVERT](https://github.com/revealapp/Revert/)|Reveal出品，一个项目教会你Swift的基本UI开发。配合reveal更加直观。
[YYKit](https://github.com/ibireme/YYKit) | YYKit 是一组庞大、功能丰富的 iOS 组件。
[SwiftGen](https://github.com/AliSoftware/SwiftGen)| This is a suite of tools written in Swift 2 to auto-generate Swift 2 code for various assets of your project: 1.enums for your Assets Catalogs 2.enums for your Localizable.strings strings.3.enums for your UIStoryboard and their Scenes. 4.enums for your UIColors.
[Instructions](https://github.com/ephread/Instructions)|新手引导
[PhoneNumberKit](https://github.com/marmelroy/PhoneNumberKit)|Swift framework for parsing, formatting and validating international phone numbers. Inspired by Google's libphonenumber.
[Aspects](https://github.com/steipete/Aspects)|再也不用自己写丑陋的`method swizzling`代码了。
[FDStackView](https://github.com/forkingdog/FDStackView) | Use UIStackView directly in iOS6+ ,百度知道团队开源代码
| [Reachability.swift](https://github.com/ashleymills/Reachability.swift) | Replacement for Apple's Reachability re-written in Swift with closures.
| [Swift Radio Pro](https://github.com/swiftcodex/Swift-Radio-Pro) | 完整的Swift 2.0的App 开源应用。
| [Advanced NSOperations sampel code](https://developer.apple.com/sample-code/wwdc/2015/downloads/Advanced-NSOperations.zip) | WWDC 2015 [Advanced NSOperations](https://developer.apple.com/videos/play/wwdc2015-226/) 的sample code
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
[Blurable](https://github.com/FlexMonkey/Blurable) | Apply a Gaussian Blur to any UIView with Swift Protocol Extensions
[Neon](https://github.com/mamaral/Neon) | A powerful Swift programmatic UI layout framework.Build dynamic and beautiful user interfaces like a boss, with Swift.|
[Async](https://github.com/duemunk/Async) | Syntactic sugar in Swift for asynchronous dispatches in Grand Central Dispatch


## 文章

标题  | 内容简介
---- | -----
[详说CMDeviceMotion](http://www.cocoachina.com/ios/20141103/10111.html)| 来自NSHipster 的翻译文章，获取陀螺仪、加速器和磁力仪(罗盘)等传感器数据，get交互灵感
[Spelunkhead](https://www.bignerdranch.com/blog/spelunkhead/)|跟着博文作者一起探索iOS系统framework。
[moby.sh](https://gist.github.com/tvon/5224569)|下载所有framework head文件，并放入一个输出文件夹中，方便搜索查看API接口，新API等。
[Facebook开源的Parse源码分析](https://github.com/ChenYilong/ParseSourceCodeStudy)|Facebook开源的Parse源码分析
[利用UIWebView打造一个炫酷的视频背景视图（OC & Swift）](http://www.cocoachina.com/ios/20151023/13860.html)| 视频背景View， 适合做Hi 5.0的登录窗口。
[Elastic view animation using UIBezierPath](http://iostuts.io/2015/10/17/elastic-bounce-using-uibezierpath-and-pan-gesture/) | Elastic view animation using UIBezierPath
[Automatically Formatting Your Objective-C](http://tonyarnold.com/2014/05/31/autoformatting-your-code.html) | 自动格式化代码工具[ClangFormat-Xcode](https://github.com/travisjeffery/ClangFormat-Xcode/)使用。
[CALayer Animation实践（一）：让应用灵动起来！](http://www.csdn.net/article/2015-09-07/2825633/1) | CALayer 动画实践（一）
[CALayer动画实践（二）：CAReplicatorLayer的用法](http://www.csdn.net/article/2015-09-09/2825659/2) | CALayer 动画实践（二）
[代码整洁之所以重要的七个理由](http://blog.jobbole.com/61312/) | 为什么代码整洁是如此重要
[技术债务：究竟让你付出了多大代价？](http://blog.jobbole.com/25137/) | 技术债务：究竟让你付出了多大代价？
[如何配置一个高效的 Mac 工作环境](http://blog.jobbole.com/63130/)| 如何配置一个高效的 Mac 工作环境
[CocoaPods的一些略为高级一丁点的使用](http://supermao.cn/cocoapodsde-xie-lue-wei-gao-ji-ding-dian-de-shi-yong/) | CocoaPods的一些略为高级一丁点的使用
[10 Things You Need to Know About Cocoa Auto Layout](http://oleb.net/blog/2013/03/things-you-need-to-know-about-cocoa-autolayout/) | 10 Things You Need to Know About Cocoa Auto Layout
[iOS Auto Layout: Fun Facts and Tips](https://www.bignerdranch.com/blog/ios-autolayout-fun-facts-and-tips/) | iOS Auto Layout: Fun Facts and Tips

##Reactive Cocoa & Functional Programming
标题  | 内容简介
---- | -----
[细说ReactiveCocoa的冷信号与热信号（一）](http://tech.meituan.com/talk-about-reactivecocoas-cold-signal-and-hot-signal-part-1.html) | 细说ReactiveCocoa的冷信号与热信号（一）
[细说ReactiveCocoa的冷信号与热信号（二）：为什么要区分冷热信号](http://tech.meituan.com/talk-about-reactivecocoas-cold-signal-and-hot-signal-part-2.html)| 细说ReactiveCocoa的冷信号与热信号（二）
[细说ReactiveCocoa的冷信号与热信号（三）：怎么处理冷信号与热信号](http://tech.meituan.com/talk-about-reactivecocoas-cold-signal-and-hot-signal-part-3.html)| 细说ReactiveCocoa的冷信号与热信号（三）
[RACSignal的Subscription深入分析](http://tech.meituan.com/RACSignalSubscription.html)| RACSignal的Subscription深入分析
[写给程序猿的范畴论 · 序](https://segmentfault.com/a/1190000003882331)|写给程序猿的范畴论 · 序
[范畴：复合的本质](http://segmentfault.com/a/1190000003883257)|范畴：复合的本质
[类型与函数](https://segmentfault.com/a/1190000003888544)|类型与函数
[范畴，可大可小](http://segmentfault.com/a/1190000003894116)|范畴，可大可小
[Kleisli 范畴](http://segmentfault.com/a/1190000003898795)|Kleisli 范畴
[积与余积](http://segmentfault.com/a/1190000003913079)|积与余积
[对单子的求索](http://garfileo.is-programmer.com/2012/8/22/monads-for-the-curious-programmer-zh_cn.35206.html)|对单子的求索
[Swift 2.0: 深入浅出 Map 和 FlatMap 概念](http://gold.xitu.io/entry/5627bfa200b0ee7f823b2fec) | 又来一篇Swift和Functional
[Enemy of the State](https://github.com/jspahrsummers/enemy-of-the-state) | 主要是讲程序设计中`state`的坏处，以及用`stateless`编程的好处。这也是近些年来`Functional Programming`重新流行起来的很重要的原因之一。BTW，推荐这个Slides也是为了安利`ReactiveCocoa`：），可以大幅度的减少iOS开发中的`state`。
[The introduction to Reactive Programming you've been missing](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754) | 虽然是针对`JavaScript`的`Rx`库的，但是对`Reactive Programming`思想描述的非常清晰明了。
[A FIRST LOOK AT REACTIVECOCOA 3.0](http://blog.scottlogic.com/2015/04/24/first-look-reactive-cocoa-3.html) | `ReactiveCocoa` 3.0的API入门文章
[REACTIVECOCOA 3.0 - SIGNAL PRODUCERS AND API CLARITY](http://blog.scottlogic.com/2015/04/28/reactive-cocoa-3-continued.html) | `ReactiveCocoa` 3.0的API入门文章

##iOS HotFix相关
标题  | 内容简介
---- | -----
[alibaba/wax](https://github.com/alibaba/wax)|Wax is a framework that lets you write native iPhone apps in Lua.
[JSPatch实现原理详解](https://github.com/bang590/JSPatch/wiki/JSPatch-%E5%AE%9E%E7%8E%B0%E5%8E%9F%E7%90%86%E8%AF%A6%E8%A7%A3) | JSPatch作者对JSPatch实现原理的详解。
[JSPatch 部署安全策略](http://blog.cnbang.net/tech/2879/) | JSPatch 部署安全策略
[JSPatch Convertor实现原理详解](http://blog.cnbang.net/tech/2915/) | JSPatch Convertor 可以自动把 Objective-C 代码转为 JSPatch 脚本。|
[JSPatch](https://github.com/bang590/JSPatch) | JSPatch bridge Objective-C and Javascript using the Objective-C runtime. You can call any Objective-C class and method in JavaScript by just including a small engine. JSPatch is generally use for hotfix iOS App.
[JSPatchConvertor](https://github.com/bang590/JSPatchConvertor)| JSPatch Convertor is a tool that converts Objective-C code to JSPatch script automatically.
[Integrating JavaScript into Native Apps](https://developer.apple.com/videos/play/wwdc2013-615/) | WWDC: Introducing a new Objective-C API to JavaScriptCore. iOS developers can now integrate scripting into their apps without having to bundle custom language interpreters. This API builds on top of the existing C API to JavaScriptCore available on Mac, and makes programming with JavaScript much easier and less error-prone.
[Web Inspector and Modern JavaScript](https://developer.apple.com/videos/play/wwdc2014-512/) | WWDC: Web Inspector, the powerful debugging tool in WebKit, is now available to JavaScriptCore-based apps. Find out how to leverage Web Inspector in your WebKit- and JavaScriptCore-based apps on iOS and OS X. Gain an overview of what's new in the JavaScript language and how to use modern JavaScript in your apps.|
[Objective-C Runtime Guide](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/ObjCRuntimeGuide/ObjCRuntimeGuide.pdf)| OC runtime相关知识， 对了解JSPatch有一定帮助。

##AsyncDisplayKit
标题  | 内容简介
---- | -----
[AsyncDisplayKit源码](https://github.com/facebook/AsyncDisplayKit)|AsyncDisplayKit源码
[AsyncDisplayKit 文档](http://asyncdisplaykit.org/guide/) | AsyncDisplayKit 文档
[Introducing AsyncDisplayKit: For smooth and responsive apps on iOS](https://code.facebook.com/posts/721586784561674/introducing-asyncdisplaykit-for-smooth-and-responsive-apps-on-ios/)|Introducing AsyncDisplayKit: For smooth and responsive apps on iOS
[Building paper](https://code.facebook.com/posts/656530327776932/building-paper/) |Building paper
[Asynchronous UI](https://www.youtube.com/watch?v=h4QDbgB7RLo)| Asynchronous UI
[Effortless Responsiveness with AsyncDisplayKit](https://www.youtube.com/v/ZPL4Nse76oY?vq=hd1080p50)| Effortless Responsiveness with AsyncDisplayKit
[AsyncDisplayKit 2.0](https://www.youtube.com/watch?v=RY_X7l1g79Q)|AsyncDisplayKit 2.0新特性介绍
[AsyncDisplayKit Google Group](https://groups.google.com/forum/#!forum/asyncdisplaykit)|AsyncDisplayKit Google Group | 
[AsyncMessagesViewController](https://github.com/nguyenhuy/AsyncMessagesViewController)| A smooth, responsive and flexible messages UI library for iOS. Built on top of the awesome AsyncDisplayKit framework, it takes full advantage of asynchronous sizing, (non-auto) layout and text rendering to deliver a 5x fps (subject to increase) scrolling experience.
[iOS App Performance: Graphics and Animations](https://developer.apple.com/videos/play/wwdc2012-238/)|iOS App Performance: Graphics and Animations
[iOS App Performance: Memory](https://developer.apple.com/videos/play/wwdc2012-242/)|iOS App Performance: Memory
[iOS App Performance: Responsiveness](https://developer.apple.com/videos/play/wwdc2012-235/)|iOS App Performance: Responsiveness

##Debug
标题  | 内容简介
---- | -----
[手把手教你如何分析 iOS 系统栈 crash](http://mp.weixin.qq.com/s?__biz=MzA3NTYzODYzMg==&mid=401345907&idx=2&sn=48a7eba21b218d8fec9dafb52b0b2b26&scene=0&key=ff7411024a07f3eb8bc0c14c5749836340744b2c4098567c144c87554887ba7c7107f1c64e7cd4261575168353bd8783)|手把手教你如何分析 iOS 系统栈 crash
[与调试器共舞 - LLDB 的华尔兹](http://objccn.io/issue-19-2/)| Xcode LLDB 详解
[使用LLDB调试程序](http://casatwy.com/shi-yong-lldbdiao-shi-cheng-xu.html)|使用LLDB调试程序

##iOS 新特性
标题  | 内容简介
---- | -----
[iOS9适配系列教程](https://github.com/ChenYilong/iOS9AdaptationTips) | iOS9适配系列教程
[iOS 9 开发高级技巧 - 通过 12 个团队所提供的技巧来快速适配 iOS 9](https://realm.io/cn/news/tips-for-ios-9-development/) | iOS 9 开发高级技巧 - 通过 12 个团队所提供的技巧来快速适配 iOS 9 |
[iOS 7 - 9新特性总结](http://anyuan.me/ios-7-9-xin-te-xing-zong-jie/) | 总结iOS7-9开发者应该关注的变化。


## 工具/插件

工具/插件  |  简介
---- | ----
[Alcatraz](http://alcatraz.io) | Xcode插件管理工具 |
[XTodo](https://github.com/trawor/XToDo) |收集项目中的所有TODO,FIXME,???, !!!，并提供了一个页面用于查看。
[Carthage](https://github.com/Carthage/Carthage) | 新的依赖管理工具 Carthage，和Cocoapods相比，Carthage是非侵入式的，不会修改xcode工程文件，只是帮助build出来frameworks。更灵活更干净。
[LANTERN](https://getlantern.org/) | 科学上网神器，速度快，稳定。
[XcodeColors](https://github.com/robbiehanson/XcodeColors) | 使 Xcode 调试控制台色彩更丰富
[ClangFormat-Xcode](https://github.com/travisjeffery/ClangFormat-Xcode/) | 代码格式化工具
[A quick reference for iOS devices.](http://iosres.com/)| iOS 设备属性查询

## 程序员的自我修养

文章  |  简介
---- | ----
[teach yourself programming in ten years](http://norvig.com/21-days.html)|Peter Norvig一篇如何学习编程。
[how to be a hacker](http://www.catb.org/esr/faqs/hacker-howto.html)|how to be a hacker
[Test-Driven Development is Stupid](http://geometrian.com/programming/tutorials/testing/test-first.php)|关于TDD的一篇文章，可以看看，以及Hacker News上的[讨论](https://news.ycombinator.com/item?id=10620275)|
[ABC: Always be coding](https://medium.com/@davidbyttow/abc-always-be-coding-d5f8051afce2#.ci0q5suo8)| 如何提（准）升（备）自（面）己（试）。
[Leveling Up](https://www.bignerdranch.com/blog/leveling-up/)|个人觉得是一篇很好的iOS进阶提升的一个好文章，推荐给有一定iOS开发经验并想继续提升自己的同学。

## 博客

博客地址 | 博主信息
------- | -------
[Garan no Dou](http://blog.ibireme.com/) | @ibireme 文章深入， 开源代码质量高，值得关注
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
[SwiftGG](http://swift.gg/) | 翻译的Swift国外优秀技术博客
