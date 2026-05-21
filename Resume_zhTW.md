# Joe Pan — 資深 iOS 工程師

**Mail:** shinren.pan@gmail.com  **GitHub:** https://github.com/shinrenpan  **Blog:** https://shinrenpan.github.io

---

## Summary

擁有 **15 年以上** iOS 實戰開發經驗，橫跨 MFI 硬體、即時通訊、影音串流、金融交易等多種 App 類型，從純 Objective-C 到現代 Swift / SwiftUI，技術演進的每個階段全程參與並持續應用至今。

專注於**架構設計**，核心立場是以 Apple 官方框架為研究基礎——深入理解 UIKit、SwiftUI、Swift Concurrency 的設計意圖，在此基礎上設計低耦合、可維護的方案，而非追隨偏離原生的第三方 Framework。這個**原生優先**的哲學同樣體現在依賴管理上：凡 Apple API 能解決的問題，優先選用原生方案，降低維護風險與 Binary Size。不執著於單一架構，進入新團隊後能快速融入現有風格，必要時自行設計更合適的方案；MVVMC 即是這個立場下的具體實踐。

多年橫跨各類 App 類型所累積的功能廣度，讓問題判斷速度極快——大多數常見功能皆有實作前例，能迅速聚焦關鍵資訊，快速找到可行解法。

---

## 技能

### 程式語言
- **Swift** 3.0 ~ 現在
- **Objective-C** 2009 ~ 現在

### UI
UIKit 與 SwiftUI 皆熟練，能獨立刻出複雜自訂介面；兩者混搭為 MVVMC 架構的核心基礎，以 `UIHostingController` 作為導航單元、SwiftUI 負責畫面渲染。早期學習 cocos2d for iPhone 奠定 2D 繪圖基礎，延伸為對 SpriteKit 的深度掌握——UIKit / SwiftUI 無法實現的動畫效果，可改以 SpriteKit 完成。

`UIKit` `SwiftUI` `UIHostingController 混搭` `AutoLayout` `Core Animation` `SpriteKit`

### 架構
不執著於單一架構，重視可維護性與團隊適應性。曾主導或參與多種架構的導入與重構，必要時自行設計更合適的方案。

`MVC` `MVVM` `Clean Swift` `TCA` `MVVMC（自研）` `@Observable / @MainActor`

### Swift Concurrency
接手既有 Swift 5+ 專案，系統性導入 Swift Concurrency 並重構至 Ready for Swift 6 相容。

`async/await` `@MainActor` `actor` `Sendable` `Task / TaskGroup`

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
`CoreBluetooth` `iBeacon`

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
**資深 iOS 工程師**　　2025/04 ~ 2026/06　　外包結束後接手，擔任公司唯一 iOS 工程師

接手外包 App 後，獨立評估程式碼品質、清償技術債，主導技術架構演進。

- **TCA 升級與移除：** 接手時版本為 1.15.2，逐步升級至 1.22.2（1.18.0 → 1.19.1 → 1.20.2 → 1.21.1 → 1.22.1 → 1.22.2）。維護與新增 Feature 期間，發現 TCA 內建 Navigation Stack 無法應對 App 非典型 Route 規則，開始著手重構，測試穩定後於 2025/09/18 正式移除。
- **自研 MVVMC 架構（[GitHub](https://github.com/shinrenpan/MVVMC)）：** 移除 TCA 後，發現 SwiftUI 原生 NavigationStack 仍無法應對複雜的非典型 Route（如結帳後同時 dismiss、切 Tab、清 stack），加上不希望整個 codebase 的架構命脈寄託於第三方套件，決定借鑒 TCA / MVI 設計概念以原生 Swift 自行設計——在 MVVM 基礎上加入 HostController（C 層）：M 層管 State / Domain Models / DTOs、VM 層以 `@Observable @MainActor` 單一入口（`doAction`）處理業務邏輯、V 層為零導航邏輯的純 SwiftUI、C 層（`UIHostingController`）擔任唯一 Router，所有導航透過 `AppRouter.shared` 集中管理。架構整理為開源 repo，並附帶 MCP Server，讓 Claude Code 在任何專案都能取得規範。
- **Swift 5 → Ready for Swift 6 重構：** 接手時 codebase 為 Swift 5+，系統性導入 `async/await`、`@MainActor`、`actor`、`Sendable`，在移除 TCA、重構 MVVMC 的過程中同步完成 Swift 6 相容遷移。
- **建置 Xcode Cloud CI/CD：** Dev 環境自動分發 TestFlight 內部測試、Production 環境自動分發 TestFlight 外部測試，全程無需人工介入。
- **App Store 上架（美國）：** 因應 SEC 合規要求僅於美國市場上架；後因 API 停止服務，App 暫時下架。
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

## Projects

### MVVMC　　[GitHub](https://github.com/shinrenpan/MVVMC)

針對 SwiftUI 原生導航的限制自行設計的四層 iOS 架構（M / VM / V / C），以 `UIHostingController` 為導航單元，`AppRouter.shared` 統一管理所有路由邏輯，SwiftUI View 保持零導航依賴。附帶可執行的 Demo 專案與 MCP Server（供 Claude Code 在任何專案取得架構規範）。

### WebParser　　[GitHub](https://github.com/shinrenpan/WebParser)

基於 WKWebView 離屏渲染的網頁解析 Swift Package，專為需要執行 JavaScript 的動態網頁（SPA、動態 DOM）設計。以泛型 Mapper 提供類型安全的解析介面（JSON → `Decodable`、自訂 Regex 擷取），全面採用 Swift 6 strict concurrency、Swift Testing 框架，GitHub Actions CI，透過 SPM 發佈。

---

## 學歷

| 學校 / 機構 | 科系 / 課程 | 期間 |
|---|---|---|
| 朝陽科技大學 | 資訊管理系（夜間部） | 2004/09 ~ 2007/01 |
| 高苑專校 | 電子工程科（五專） | — |
| 資策會數位內容學院 | iOS 開發課程（六個月） | 2009 |

> 結業作品：以 cocos2d for iPhone 開發音樂節奏遊戲《擋十個》，榮獲 **2009 數位內容系列競賽手機遊戲創作組金獎**。結業後與同學接案開發[音樂 App](https://www.youtube.com/watch?v=npV4b-Z9A4w&t=177s)。

**語言：** 中文（母語）　英文（讀寫可應對技術文件）
