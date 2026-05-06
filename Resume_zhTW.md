# Joe Pan — 資深 iOS 工程師

**Mail:** shinren.pan@gmail.com  **GitHub:** https://github.com/shinrenpan  **Blog:** https://shinrenpan.github.io

---

## Summary

擁有 **15 年以上** iOS 實戰開發經驗，橫跨 MFI 硬體、即時通訊、影音串流、金融交易等多種 App 類型，從純 Objective-C 到現代 Swift / SwiftUI，技術演進的每個階段全程參與並持續應用至今。

專注於**架構設計與重構**——主導 ObjC → Swift 遷移、設計 UIHostingController + SwiftUI 混合導航架構，皆以「可維護、低耦合、可掌控」為核心目標。不執著於單一架構，進入新團隊後能快速理解並融入現有風格，必要時自行設計更合適的方案。

秉持**原生優先**哲學：凡 Apple 原生 API 能解決的問題，優先使用原生方案，避免引入不必要的第三方依賴，降低維護風險與 Binary Size。

近期系統性導入 **AI 輔助工具鏈**（Claude + Skill 規範），建立可複用的架構規範文件，讓 AI 依照專案既有風格快速產出符合規範的代碼，進一步提升個人開發效能。

---

## 技能

### 程式語言
- **Swift** 3.0 ~ 現在
- **Objective-C** 2009 ~ 現在

### UI
UIKit 與 SwiftUI 皆熟練，能獨立刻出複雜自訂介面；兩者混搭（UIHostingController + SwiftUI）為目前主要架構模式。早期學習 cocos2d for iPhone 奠定 2D 繪圖基礎，延伸為對 SpriteKit 的深度掌握——UIKit / SwiftUI 無法實現的動畫效果，可改以 SpriteKit 完成。

`UIKit` `SwiftUI` `UIHostingController 混搭` `AutoLayout` `Core Animation` `SpriteKit`

### 架構
不執著於單一架構，重視可維護性與團隊適應性。曾主導或參與多種架構的導入與重構，必要時自行設計更合適的方案。

`MVC` `MVVM` `Clean Swift` `TCA` `UIHostingController + SwiftUI 自研架構` `@Observable / @MainActor`

### 網路
以 URLSession 為主（原生優先），視需求使用 gRPC；Alamofire 等第三方亦有實務使用經驗。

`URLSession` `gRPC (grpc-swift / connect-swift)` `Alamofire`

### 即時通訊
市面上主流協議皆有實際專案參與經驗，涵蓋文字通訊與影音串流。

`WebSocket` `XMPP` `MQTT` `SignalR` `VOIP` `Live Streaming (HaishinKit / ijkplayer / ReplayKit)`

### 資料庫
以原生方案為優先，主流第三方亦有使用經驗。

`CoreData` `SwiftData` `KeyChain` `NSKeyedArchiver` `Realm` `fmdb`

### 藍芽
`BLE 4.0` `iBeacon`

### 工具鏈

| 類別 | 工具 |
|------|------|
| 版本控制 | Git |
| 套件管理 | Swift Package Manager、CocoaPods、Carthage |
| Project 管理 | XcodeGen、Tuist |
| CI / CD | Xcode Cloud、Jenkins、Fastlane、Firebase App Distribution |
| AI 開發加速 | Claude（CLAUDE.md + Skill 規範，系統化提升 Feature 開發效率） |

---

## 工作經歷

### DRACO EVOLUTION
**資深 iOS 工程師**　　2025/04 ~ 迄今　　外包結束後接手，現為公司唯一 iOS 工程師

接手外包 App 後，獨立評估程式碼品質、清償技術債，並持續迭代至今。

- **TCA 升級與移除：** 接手時版本為 1.15.2，逐步升級至 1.22.2（1.18.0 → 1.19.1 → 1.20.2 → 1.21.1 → 1.22.1 → 1.22.2）。維護與新增 Feature 期間，發現 TCA 內建 Navigation Stack 無法應對 App 非典型 Route 規則，開始著手重構，測試穩定後於 2025/09/18 正式移除。
- **自研 UIHostingController + SwiftUI 混合導航架構：** 以 `UIHostingController` 為導航單元、SwiftUI 負責畫面渲染——每個 Feature 由 `FeatureHostController` 持有 ViewModel，路由邏輯集中於 Host 層，SwiftUI 側保持無 UIKit 依賴，達到低耦合、易維護的目標，並整理成內部 Skill 規範。
- **建置 Xcode Cloud CI/CD：** Dev 環境自動分發 TestFlight 內部測試、Production 環境自動分發 TestFlight 外部測試，全程無需人工介入。
- **導入 AI 工具鏈（Claude + Skill）：** 建立 `CLAUDE.md` 與多份 Skill 文件（SwiftUI、ViewModel、HostController、Model、Swift Concurrency 等），讓 Claude 依照專案架構快速產出符合規範的 Feature 代碼，顯著縮短開發週期。

---

### 皆凱科技
**iOS 工程師**　　2023/09 ~ 2024/09　　三人 iOS 團隊主力，其餘兩位同事分別專責內部 KLine 套件與另一套 VPN App

負責金融交易平台與 [金田GT](https://apps.apple.com/tw/app/id6467499244)（貴金屬交易理財 App）兩套 App 的維護，並參與基於 Tinode 的 IM 軟體開發。

**金融交易 App（[參考影片](https://www.youtube.com/watch?v=4xdZ6mtfEa0)）**

- 導入 XcodeGen 管理 Project，消除多人協作時 `.xcodeproj` 的 Git 衝突。
- 以 SignalR 介接即時報價資料，搭配 `CADisplayLink + RunLoop` 解決 UICollectionView 拖動時 Cell 更新卡頓問題。
- 使用 UICollectionView 全面替代 UITableView，統一列表 UI 實作方式，以利後續支援複雜佈局與更彈性的 Cell 組合；維護與新增公司內部 KLine 套件。
- 撰寫 Script 自動切換 dev / qat / production 環境，實作 App 內即時語系切換。

**[金田GT](https://apps.apple.com/tw/app/id6467499244) App（[參考影片](https://youtu.be/Rh_pZrOLsh0)）**

- Swift / Objective-C 混編開發，導入 gRPC 介接資料。
- 基於 [Rate Limiting UITableView/UICollectionView Reloads](http://www.enharmonichq.com/rate-limiting-uitableview-and-uicollectionview-reloads/) 的思路，解決高頻 gRPC 資料變動時 reload 過度頻繁的效能問題。
- 實作審核模式下隱藏特定 UI 功能，順利通過 App Store 審查。
- 以 Jenkins + Fastlane 建立 CI/CD，Firebase 分發 dev / qat 測試包。
- 導入 Xcode 15 Asset Symbol Generation；實作 App 與 HTML5 網站雙向互動（JavaScript Bridge）。

**IM 軟體（基於 Tinode）**

- 為大幅客製化 Tinode 預設介面，移除 Storyboard 改以 Hardcoded UI 實作，提升改版彈性。
- 公司缺乏 Golang 工程師，為準確理解 Server 行為、評估 IM 功能邊界，主動學習 Golang 並研讀 Tinode Server 端程式碼。

---

### 恒遠科技
**iOS 工程師**　　2022/04 ~ 2023/07　　獨立負責整個 iOS 專案（[參考影片](https://youtu.be/vgyh0lbtPYY)）

接手大陸同事 Objective-C 專案，主導技術轉型。App 包含短影音、長影音、漫畫、小說、遊戲、直播、聊天等功能。

- **主導 ObjC → Swift 遷移：** 制定漸進式策略，新功能 100% Swift 開發，舊模組逐步重構。
- 導入 XcodeGen 解決 Git Project 衝突；研究 Tuist 並評估兩者差異。
- **重構短影音本地播放架構：** 原架構以 GCDWebServer 架設本地伺服器播放下載的 m3u8，維護成本高。重構為自訂 `AVAssetResourceLoaderDelegate` 方案——將 `file://` scheme 替換為自訂 `local://`，讓 AVPlayer 將請求交給 Delegate 處理，Delegate 換回 `file://` 讀取本地資料回應，移除 GCDWebServer 依賴，降低 Binary Size（[參考文章](https://shinrenpan.github.io/2022-07-13/)）。
- 實作漫畫閱讀器、小說閱讀器、遊戲嵌入頁面，三者皆透過 WebView 與 Native 層雙向溝通。
- 導入合作方以 Flutter 開發的直播套件，處理 Flutter module 嵌入 Native 的整合問題，並跨 framework 進行 debug。
- 對接第三方簽名廠商發佈 App（企業內部發佈，繞過 App Store 審核流程）。

---

### 遊戲橘子集團
**iOS 約聘工程師**　　2019/06 ~ 2022/02

**[BeanFun](https://apps.apple.com/tw/app/beanfun/id1108282446) App**

- 與團隊共同導入 Clean Swift 架構，將 Objective-C 模組逐步重構為 Swift。
- BeanFun 大量功能以 WebView 承載並需支援 Hot Reload，深度實作 WebView ↔ Native App 雙向溝通機制，涵蓋 JavaScript Bridge 設計、事件傳遞與頁面狀態同步。

---

### 遊戲橘子集團
**iOS 約聘工程師**　　2018/09 ~ 2019/03　　主力負責 iOS 開發

**In-House 企業管理 App「teamup!」**

橘子集團內部專案管理與簽核平台，支援即時通訊、線上簽核與門禁整合，曾於執行長劉柏園前進南極期間作為遠端管理工具（[參考報導](https://www.bnext.com.tw/article/51537/gamania-teamup)）。

- 針對低頻寬環境優化：以 fmdb 快取 API 資料實現離線使用，實作多層次圖片快取（縮圖優先展示、背景下載原圖替換），確保弱網下 App 仍可正常操作。

---

### 緯創軟體
**iOS 工程師**　　2016/08 ~ 2018/03

駐點於國泰人壽，實際為[國泰人壽 App](https://itunes.apple.com/tw/app/id432046643) 主要維護者。原始專案以 Objective-C 開發，因應國泰內部引入 Swift 的技術決策，負責新功能以 Swift 實作，並逐步推動 Objective-C 模組的重構與過渡。

---

### 和特資訊
**iOS 工程師**　　2016/03 ~ 2016/06

參與新創飯店企業管理 App 開發，供飯店員工進行排班管理、即時回報與打卡簽到。後端選用 SignalR 實作聊天功能——在 XMPP、MQTT 為業界主流的時期，為少見的技術選型，從中累積了 SignalR 協議的第一手實作經驗。另實作基於 Core Location 的地點限制打卡機制。

---

### 互聯網行動科技
**iOS 工程師**　　2015/04 ~ 2016/01

依老闆構想開發購物商城 App，核心概念是讓使用者透過內嵌遊戲（靈感來自 Tap Titans 玩法）獲得虛擬幣或優惠券，再於商城內使用。基於 XMPP 實作聊天功能，並以 SpriteKit 開發遊戲模組，是第一次將遊戲引擎整合進電商 App 的實戰經驗。

---

### 其他早期經歷（2010 ~ 2015）

| 公司 | 期間 | 主要內容 |
|------|------|----------|
| PiPiMy | 2015/01 ~ 2015/03 | C2C 二手交易 App（Beta） |
| 時間軸科技 | 2012/05 ~ 2014/06 | 套版商城 App 架構設計 / [優惠券 App](https://itunes.apple.com/tw/app/id551945238) |
| JamZoo | 2012/11 ~ 2013/06 | 將「單身銀行」App 聊天機制由 Timer Polling 重構為 MQTT（參考 Facebook 採用 MQTT 的技術決策），解決輪詢造成的卡頓問題；另開發[離線租車 App](https://www.youtube.com/watch?v=aail3KJdb4c)、HTML5 電子書 WebView |
| 汎美達電信 | 2010/09 ~ 2012/02 | [Media Player 互動 App](https://www.youtube.com/watch?v=Unv4XT5EjNI)、[小遊戲](https://www.youtube.com/watch?v=fLPyCJoCQWY)、BLE |
| 旭揚半導體 | 2010/03 ~ 2010/07 | [MFI 外接硬體 App](https://www.youtube.com/watch?v=ZVgwwkCCrUQ)、網路電台、Local 音樂播放 |

---

## 學歷

| 學校 / 機構 | 科系 / 課程 | 期間 |
|---|---|---|
| 朝陽科技大學 | 資訊管理系（夜間部） | 2004/09 ~ 2007/01 |
| 高苑專校 | 電子工程科（五專） | — |
| 資策會數位內容學院 | iOS 開發課程（六個月） | 2009 |

> 結業作品：以 cocos2d for iPhone 開發音樂節奏遊戲《擋十個》，榮獲 **2009 數位內容系列競賽手機遊戲創作組金獎**。結業後與同學接案開發[音樂 App](https://www.youtube.com/watch?v=npV4b-Z9A4w&t=177s)。

**語言：** 中文（母語）　英文（讀寫可應對技術文件）
