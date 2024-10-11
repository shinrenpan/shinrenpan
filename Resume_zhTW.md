
Name: Joe Pan  
Mail: shinren.pan@gmail.com  
GitHub: https://github.com/shinrenpan  
Blog: https://shinrenpan.github.io  

# Summary

iOS 工程師.
自 2009 年開發 iOS App, 擁有 **10年** 以上 iOS App 開發經驗.  
開發過的 App 類型:

- 購物商城
- 聊天軟體
- 藍芽 4.0 以上, 或是 iBeacon
- 2D 遊戲
- 影音串流
- 音樂串流
- MFI

# 技能

## 程式語言

- Objective-C 2009 ~ present
- Swift 3.0 ~ present

## 語言

- 中文 (母語)
- 英文 (普)

## iOS 技能

- UI
  - Interface Builder (XIB)
  - Storyboard
  - Hardcoded
  - AutoLayout
  - Autoresizing
  - [SwiftUI]
  - Core Animation
  - [SpriteKit]

- API Communication
  - URLSession
  - gRPC with [grpc-swift](https://github.com/grpc/grpc-swift), [connect-swift](https://github.com/connectrpc/connect-swift)
  - 3rd-Paryty Library ([Alamofire]... etc)
  - ~~NSURLConnection~~

- Instant Message
  - XMPP with [XMPPFramework]
  - MQTT with [MQTT-Client-Framework]
  - Socket with [NSStream]
  - SignalR with [SignalR-ObjC], [SignalR-Client-Swift](https://github.com/moozzyk/SignalR-Client-Swift)
  - Live streaming with [ijkplayer], [HaishinKit], [ReplayKit]
  - VOIP

- Database
  - CoreData
  - KeyChain
  - [fmdb]
  - [Realm]
  - NSKeyedArchiver / NSkeyedUnarchiver
  - Plist
  - NSUserDefaults

- BlueTooth
  - BLE 4.0 or iBeacon

- Gaming
  - [SpriteKit] for 2D game

- Version control
  - Git

- 3rd-Party Managment
  - [Swift-Package-Manager]
  - [CocoaPods]
  - [Carthage]

# 工作經歷

## 皆凱科技

### iOS 工程師 2023/09 ~ 2024/09

開發與維護公司金融 App, 參考[影片10].  

工作內容:

- 使用 [MVVVR] 架構開發.
- 導入 [XcodeGen] 管理 Project.
- 使用 [SignalR] 介接資料.
- 客製化 UI.
- 使用 UICollectionView 替代 UITableView 實作列表 UI.
- 撰寫 Script 切換 dev / qat / production 環境.
- App 內切換語系實作.
- 維護與新增公司內部 KLine 套件.
- 使用 CADisplayLink + RunLoop 實現 UICollectionView 拖動時能正常更新 Cell.

開發與維護公司 [金田GT] App, 參考[影片9].

工作內容:

- 使用 Swift 開發維護 App, 並與 3rd-party Objective-C 混編.
- 使用 [MVVVR] 架構開發.
- 導入 [XcodeGen] 管理 Project.
- 實作 App 審核時, 隱藏 UI 功能.
- 客製化 UI.
- 使用 [gRPC] 介接資料.
- 基於[文章2], 避免 UITableView 在接收 gRPC 資料變動時, reload 太頻繁.
- 使用 [Jenkins] + [Fastlane] 實作簡易 CI / CD.
- 使用 [Firebase] 分發 dev / qat 環境 App.
- 撰寫 Script 切換 dev / qat / production 環境.
- 導入 Xcode 15 新功能 [Asset symbol generation].
- HTML5 網站與 app 交互.
- 使用 [Swift-Package-Manager] / [CocoaPods] 管理套件.

基於 [Tinode] 開發 IM 軟體.

工作內容:

- 將 iOS Client 從 MVC 改為 [MVVVR] 架構.
- 移除 Storyboard, 改使用 Hardcoded 方式實作 UI, 較容易客製化 UI.
- 學習 Golang 並研讀 Server 端程式碼

## 恒遠科技

### iOS 工程師 2022/04 ~ 2023/07

開發與維護公司 App, 參考[影片8].

> 使用手機錄影, 長短影片功能無法正常顯示.

App 內容包含:

- 短影音
- 長影音
- 漫畫
- 小說
- 遊戲
- 直播
- 聊天

工作內容:

- 接手大陸同事 Objective-C 專案, 並維護.
- 使用 Swift 開發新功能, 與 Objective-C 混編.
- 導入 [XcodeGen] 管理 Project, 避免 Project 常產生 Git 衝突.
- 研究 [Tuist] 與 [XcodeGen] 差異.
- 主導專案由 Objective-C 逐漸轉換成 Swift.
- 導入 [MVVVR] 架構開發.
- 移除常年不維護第三方套件, 使用原生 API 替代.
- 移除使用 [GCDWebServer] 播放本地端 m3u8, 使用原生 API 替代, 參考[文章1].
- 撰寫 Script 切換環境.
- 實作漫畫閱讀器.
- 實作小說閱讀器.
- 實作遊戲 Web 與 App 交互.
- 導入合作方直播套件.
- 與第三方簽名廠商溝通發佈 App, 不上架至 App Store.

## 遊戲橘子集團

### iOS 約聘工程師 2019/06 ~ 2022/02

開發與維護 [BeanFun] App.

工作內容:

- 與主管及同事, 導入 [Clean Swift] 架構.
- 修正 Objective-C 既有 bug, 並使用 Swift 重構.
- 使用 Swift 開發新功能, 與 Objective-C 混編.
- 實作大量 WebView 與 App 交互.

### iOS 約聘工程師 2018/09 ~ 2019/03

開發與維護 In-House 專案管理 App, 讓集團內員工透過 App 掌控專案進度.

工作內容:

- 使用 Objective-C 開發與維護 App
- 透過 [fmdb] 暫存 API 資料, 達到離線使用.
- 實作圖片暫存機制, 本地端有圖片就先使用, 沒有的話, 先下載縮圖呈現在畫面, 之後再下載原圖.

## 緯創軟體

### iOS 工程 2016/08 ~ 2018/03

駐點於國泰人壽, 開發與維護[國泰人壽] App.

工作內容:

- 維護現有 App Objective-C bug.
- 使用 Swift 開發新功能.
- 逐漸汰換 Objective-C, 使用 Swift 重構

## 和特資訊

### iOS 工程師 2016/03 ~ 2016/06

開發飯店內部管理系統 App, 可讓飯店員工打卡或是透過 App 即時傳送訊息.

工作內容:

- 使用 Objective-C 實作開發.
- 基於 [SignalR] 開發聊天功能.
- 實作限制地點打卡功能, 基於 Core Location.

## 互聯網行動科技

### iOS 工程師 2015/04 ~ 2016/01

開發與實作老闆發想的 App.

工作內容:

- 使用 Objective-C 實作開發.
- 基於 [XMPP] 開發聊天功能
- 基於 [SpriteKit] 開發遊戲功能.
- 實作購物商城功能.

## PiPiMy

### iOS 工程師 2015/01 ~ 2015/03

開發 ~~[行動拍拍賣]~~ Beta 版本, 二手 C2C 交易 App.

工作內容:

- 使用 Objective-C 實作開發.

## 時間軸科技

### iOS 工程師 2013/09 ~ 2014/06

開發套版類型 App 機制, 讓廠商可透過 App 開店.

工作內容:

- 使用 Objective-C 實作開發.
- 開發套版類型 App 架構.
- 與後端同事討論如何使用套版機制.

### iOS 工程師 2012/05 ~ 2012/08

開發 [巷弄] beta 第一版, 優惠券類型 App.

工作內容:

- 使用 Objective-C 實作開發.
- Memory management.
- 使用 Xcode Instruments 檢測 Memory leak 與其他事項.
- 使用 AutoLayout 取代 AutoResizing.
- UI 卡頓問題.

## JamZoo

### iOS 工程師 2012/11 ~ 2013/06

接案公司, 開發大量 App.

工作內容:

- 使用 Objective-C 實作開發.
- 重構 ~~[單身銀行]~~ 聊天機制, 使用 [MQTT] 替代定時 Polling.
- 研究其他聊天機制, 例如 [XMPP], Socket.
- 開發租車業者 In-House App, 並實作離線功能, 參考[影片7].
- 開發美髮業者 In-House App.
- 與工研院廠商合作基於 HTML5 電子書瀏覽器 App, 並實作 UIWebVIew 與 App 互通.

## 汎美達電信

### iOS 工程師 2010/09 ~ 2012/02

接案公司, 開發大量 App.

工作內容:

- 使用 Objective-C 實作開發.
- 透過 NSURLConnection 與 api 介接取得資料
- 透過 Media Player Framework 實作互動 App, 參考[影片3]
- 使用 UIKit 製作小遊戲功能, 參考[影片4], [影片5]
- 實作可下載 Skin 功能之 App, 參考[影片6]
- 實作其他未接觸功能, 例如 SQLite, BLE...

## 旭揚半導體

### iOS 工程師 2010/03 ~ 2010/07

開發與維護基於 MFI 硬體外之接 App, 參考[影片2].

工作內容:

- 使用 Objective-C 實作開發.
- 開發新功能網路免費電台.
- 開發新功能播放本地音樂.
- 實作 Twitter, Facebook 分享功能.
- 學習 [External Accessory Framework].

# 學歷

## 資策會數位-數位內容學院

iOS 學習階段2009 (六個月)

學習內容:

- 學習 Objective-C 基礎
- 學習 [cocos2d for iPhone]

結業時與其他兩位學院同學一起使用 [cocos2d for iPhone] 開發出擋十個音樂節奏遊戲,  
拿下 2009 數位內容係列競賽手機遊戲創作組金獎.

與學院同學結業後, 接案開發音樂 App, 參考[影片1].

## 朝陽科技大學

資訊管理系夜間部畢業 (2004-09 ~ 2007-01)

## 高苑專校

五專電子工程科畢業

[文章1]: https://shinrenpan.github.io/05/
[文章2]: http://www.enharmonichq.com/rate-limiting-uitableview-and-uicollectionview-reloads/

[影片1]: https://youtu.be/npV4b-Z9A4w?t=177
[影片2]: https://www.youtube.com/watch?v=ZVgwwkCCrUQ
[影片3]: https://www.youtube.com/watch?v=Unv4XT5EjNI
[影片4]: https://www.youtube.com/watch?v=fLPyCJoCQWY
[影片5]: https://www.youtube.com/watch?v=khn3skxDjls
[影片6]: https://www.youtube.com/watch?v=197C74y68Oo
[影片7]: https://www.youtube.com/watch?v=aail3KJdb4c
[影片8]: https://youtu.be/vgyh0lbtPYY
[影片9]: https://youtu.be/Rh_pZrOLsh0
[影片10]: https://www.youtube.com/watch?v=4xdZ6mtfEa0

[MQTT]: http://mqtt.org
[XMPP]: https://xmpp.org
[cocos2d for iPhone]: https://zh.wikipedia.org/wiki/Cocos2d
[SignalR]: https://learn.microsoft.com/zh-tw/aspnet/signalr/overview/getting-started/introduction-to-signalr
[Clean Swift]: https://clean-swift.com/
[MVVVR]: https://shinrenpan.github.io/01/
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
[Swift-Package-Manager]: https://www.swift.org/package-manager/
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
