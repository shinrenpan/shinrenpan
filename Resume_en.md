
Name: Joe Pan  
Mail: shinren.pan@gmail.com  
GitHub: https://github.com/shinrenpan  
Blog: https://shinrenpan.github.io

# Summary

iOS Engineer with over 10 years of experience developing iOS apps since 2009. 

Types of apps developed:
- E-commerce
- Chat
- Bluetooth 4.0 or iBeacon
- 2D games
- Video streaming
- Music streaming
- MFI

# Skills

## Programming Languages

- Objective-C (2009 - present)
- Swift (3.0 - present)

## Languages

- Mandarin (Native)
- English (Intermediate)


## iOS Skills

- UI Development
  - Interface Builder (XIB)
  - Storyboard
  - Hardcoded UI
  - AutoLayout
  - Autoresizing
  - [SwiftUI]
  - Core Animation
  - [SpriteKit]

- API Communication
  - URLSession
  - gRPC with [grpc-swift], [connect-swift]
  - 3rd-Party Libraries (e.g., [Alamofire])
  - ~~NSURLConnection~~ (deprecated)

- Instant Messaging
  - XMPP with [XMPPFramework]
  - MQTT with [MQTT-Client-Framework]
  - Socket with [NSStream]
  - SignalR with [SignalR-ObjC], [SignalR-Client-Swift](https://github.com/moozzyk/SignalR-Client-Swift)
  - Live streaming with [ijkplayer], [HaishinKit], [ReplayKit]
  - VOIP

- Databases
  - CoreData
  - KeyChain
  - [FMDB]
  - [Realm]
  - NSKeyedArchiver/Unarchiver
  - Plist
  - NSUserDefaults

- Bluetooth
  - BLE 4.0 or iBeacon integrations

- Game Development
  - [SpriteKit] for 2D game development

- Version Control
  - Git

- 3rd-Party Package Management
  - [Swift Package Manager]
  - [CocoaPods]
  - [Carthage]


# Work Experience

## DRACO EVOLUTION

### iOS Engineer 2025/04 ~ Present

Developed and maintained the company’s app.

- Assumed ownership of a previously outsourced application built with SwiftUI and [TCA] (The Composable Architecture).
- Managed the incremental upgrade of the [TCA] library from version 1.10.4 to the latest stable release, ensuring code modernity and stability.

## EVERVICTORY TECHNOLOGY

### iOS Engineer 2023/09 - 2024/09

Developed and maintained the company’s finance app, [video10]

- Developed using the [MVVVR] architecture.
- Managed projects with [XcodeGen].
- Integrated data using [SignalR].
- Customized UI.
- Used UICollectionView instead of UITableView for list UI.
- Wrote scripts to switch between dev, qat, and production environments.
- Implemented in-app language change.
- Maintained and expanded the company’s KLine framework.
- Used CADisplayLink + RunLoop to ensure smooth cell updates during UICollectionView dragging.

Developed and maintained the [金田GT] app, [video9]

- Developed and maintained using Swift, with mixed integration of 3rd-party Objective-C.
- Implemented the [MVVVR] architecture.
- Managed projects with [XcodeGen].
- Implemented hidden UI features for app review.
- Customized UI.
- Integrated data using [gRPC].
- Optimized UITableView to avoid excessive reloads when receiving gRPC data updates, based on [Article2].
- Set up simple CI/CD using [Jenkins] and [Fastlane].
- Distributed apps via [Firebase] for dev/qat environments.
- Introduced Xcode 15’s new [Asset symbol generation].
- Integrated interactions between HTML5 websites and the app.
- Managed dependencies with [Swift Package Manager] and [CocoaPods].

IM Software Development based on [Tinode]

- Refactored the iOS client from MVC to [MVVVR] architecture.
- Removed Storyboard and implemented UI using hardcoded methods for easier customization.
- Learned Golang and studied server-side code.

## HengYuan Technology Co. Ltd

### iOS Engineer 2022/04 ~ 2023/07

Developed and maintained the company’s app, which included features such as short/long videos, comics, novels, games, live streaming, and chat. [video8]

- Took over and maintained a legacy Objective-C project from a colleague in China.
- Developed new features using Swift while integrating with Objective-C.
- Introduced [XcodeGen] for project management to avoid frequent Git conflicts.
- Researched the differences between [Tuist] and [XcodeGen].
- Led the gradual migration of the project from Objective-C to Swift.
- Implemented the [MVVVR] architecture for development.
- Removed unmaintained third-party libraries, replacing them with native APIs.
Replaced [GCDWebServer] for local m3u8 playback with native APIs, based on [Article1].
- Wrote scripts for environment switching.
- Developed a comic reader and a novel reader.
- Integrated web and app interactions for games.
- Introduced a live streaming SDK from a partner.
- Coordinated with a third-party signing service to distribute the app without releasing it to the App Store.

## Gamania Group

### iOS Contract Engineer 2019/06 ~ 2022/02

Developed and maintained the [BeanFun] App.

- Collaborated with the team to introduce the [Clean Swift] architecture.
- Fixed existing bugs in Objective-C and refactored code using Swift.
Developed new features in Swift while integrating with existing Objective-C code.
- Implemented extensive interactions between WebView and the app.

### iOS Contract Engineer 2018/09 ~ 2019/03

Developed and maintained an in-house project management app that enabled employees to track project progress.

- Developed and maintained the app using Objective-C.
- Cached API data using [FMDB] to enable offline functionality.
- Implemented an image caching mechanism that first displayed thumbnails, then downloaded and displayed full-size images.

## Wistron Software

### iOS Engineer 2016/08 ~ 2018/03

Developed and maintained the [國泰人壽] App.

- Maintained the existing app by fixing Objective-C bugs.
- Developed new features using Swift.
- Gradually replaced Objective-C code with Swift through refactoring.

## HOTELITYIN CO. LTD

### iOS Engineer 2016/03 ~ 2016/06

Developed an internal management system app for hotel staff to clock in and send real-time messages.

- Implemented the app using Objective-C.
- Developed the chat feature based on [SignalR].
- Implemented location-based clock-in functionality using Core Location.

## 互聯網行動科技

### iOS Engineer 2015/04 ~2016/01

Developed and implemented app ideas proposed by the company's founder.

- Implemented the app using Objective-C.
- Developed a chat feature based on [XMPP].
- Created game functionality using [SpriteKit].
- Developed an e-commerce feature.

## PiPiMy

### iOS Engineer 2015/01 ~ 2015/03

Developed the beta version of the C2C secondhand trading app [行動拍拍賣].

- Implemented the app using Objective-C.

## Hiiir

### iOS Engineer 2013/09 ~ 2014/06

Developed a templated app mechanism that allowed businesses to open stores via the app.

- Implemented the app using Objective-C.
- Developed the templated app architecture.
- Collaborated with backend developers to establish the templating mechanism.

### iOS Engineer 2012/05 ~ 2012/08

Developed the beta version of [巷弄], a coupon-based app.

- Implemented the app using Objective-C.
- Managed memory and optimized performance.
- Used Xcode Instruments to detect memory leaks and other issues.
- Replaced AutoResizing with AutoLayout.
- Resolved UI performance issues, ensuring smoother interactions.

## JamZoo

### iOS Engineer 2012/11 ~ 2013/06

Developed a variety of apps for clients.

- Implemented apps using Objective-C.
- Refactored the chat mechanism in the [單身銀行] app, replacing polling with [MQTT].
- Researched other chat technologies, such as [XMPP] and Socket.
- Developed an in-house app for a car rental company with offline functionality, [video7].
- Developed an in-house app for a hairdressing company.
- Collaborated with ITRI to develop an HTML5-based eBook reader app, integrating UIWebView for communication between the web and app.

## Viamedia Mobile Corporation

### iOS Engineer 2010/09 ~ 2012/02

Developed a variety of apps for clients.

- Implemented apps using Objective-C.
- Fetched data from APIs using NSURLConnection.
- Developed interactive apps using the Media Player Framework, [video3].
- Created games using UIKit, [video4], [video5].
- Implemented apps with downloadable skin functionality, [video6].
- Explored additional features like SQLite and BLE.

## KeyStone Semiconductor Corp.

### iOS Engineer 2010/03 ~ 2010/07

Developed and maintained an app connected to MFI hardware, [video2].

- Implemented the app using Objective-C.
- Developed new features such as online radio and local music playback.
- Implemented social sharing features for Twitter and Facebook.
- Gained experience with the [External Accessory Framework].

# Education

## Institute for Information Industry (III)

iOS Development Program (2009 – Six Months)

- Learned the fundamentals of Objective-C.
- Studied [Cocos2d for iPhone].

At the end of the program, collaborated with two other students to develop a rhythm-based game using [Cocos2d for iPhone], which won the Gold Award in the 2009 Digital Content Series Mobile Game Creation Competition.

Post-graduation, collaborated with academy classmates on contract development for a music app, [video1].

## Chaoyang University of Technology

Bachelor's in Information Management (Evening Program, 2004/09 – 2007/01)

## Kao Yuan University

Associate Degree in Electronic Engineering



[Article1]: https://github.com/shinrenpan/shinrenpan/discussions/15
[Article2]: http://www.enharmonichq.com/rate-limiting-uitableview-and-uicollectionview-reloads/

[video1]: https://youtu.be/npV4b-Z9A4w?t=177
[video2]: https://www.youtube.com/watch?v=ZVgwwkCCrUQ
[video3]: https://www.youtube.com/watch?v=Unv4XT5EjNI
[video4]: https://www.youtube.com/watch?v=fLPyCJoCQWY
[video5]: https://www.youtube.com/watch?v=khn3skxDjls
[video6]: https://www.youtube.com/watch?v=197C74y68Oo
[video7]: https://www.youtube.com/watch?v=aail3KJdb4c
[video8]: https://youtu.be/vgyh0lbtPYY
[video9]: https://youtu.be/Rh_pZrOLsh0
[video10]: https://www.youtube.com/watch?v=4xdZ6mtfEa0

[MQTT]: http://mqtt.org
[XMPP]: https://xmpp.org
[cocos2d for iPhone]: https://zh.wikipedia.org/wiki/Cocos2d
[SignalR]: https://learn.microsoft.com/zh-tw/aspnet/signalr/overview/getting-started/introduction-to-signalr
[Clean Swift]: https://clean-swift.com/
[MVVVR]: https://github.com/shinrenpan/shinrenpan/discussions/18
[gRPC]: https://grpc.io

[單身銀行]: https://itunes.apple.com/tw/app/單身銀行-實名制-未婚身份認證/id672623637?mt=8
[巷弄]: https://itunes.apple.com/tw/app/巷弄-美食餐廳半價優惠/id551945238?mt=8
[行動拍拍賣]: https://itunes.apple.com/app/id1049599582
[國泰人壽]: https://itunes.apple.com/tw/app/id432046643
[BeanFun]: https://apps.apple.com/tw/app/beanfun/id1108282446
[金田GT]: https://apps.apple.com/tw/app/id6467499244

[External Accessory Framework]: https://developer.apple.com/documentation/externalaccessory
[SpriteKit]: https://developer.apple.com/library/ios/documentation/SpriteKit/Reference/SpriteKitFramework_Ref/
[Asset symbol generation]: https://sarunw.com/posts/swift-symbols-for-asset-catalog/
[Swift Package Manager]: https://www.swift.org/package-manager/
[ReplayKit]: https://developer.apple.com/documentation/replaykit
[SwiftUI]: https://developer.apple.com/documentation/swiftui

[fmdb]: https://github.com/ccgus/fmdb
[XcodeGen]: https://github.com/yonaskolb/XcodeGen
[Tuist]: https://tuist.io
[GCDWebServer]: https://github.com/swisspol/GCDWebServer
[Tinode]: https://github.com/tinode
[Jenkins]: https://www.jenkins.io
[Fastlane]: https://fastlane.tools
[Firebase]: https://firebase.google.com
[CocoaPods]: https://cocoapods.org
[Carthage]: https://github.com/Carthage/Carthage
[Realm]: https://realm.io
[XMPPFramework]: https://github.com/robbiehanson/XMPPFramework
[MQTT-Client-Framework]: https://github.com/ckrey/MQTT-Client-Framework
[NSStream]: https://developer.apple.com/library/ios/documentation/Cocoa/Reference/Foundation/Classes/NSStream_Class/
[SignalR-ObjC]: https://github.com/DyKnow/SignalR-ObjC
[Hotelityin]: http://www.hotelityin.com
[ijkplayer]: https://github.com/bilibili/ijkplayer
[Alamofire]: https://github.com/Alamofire/Alamofire
[HaishinKit]: https://github.com/shogo4405/HaishinKit.swift
[grpc-swift]: https://github.com/grpc/grpc-swift
[connect-swift]: https://github.com/connectrpc/connect-swift
[TCA]: https://github.com/pointfreeco/swift-composable-architecture
