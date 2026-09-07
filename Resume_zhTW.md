# Joe Pan — 資深 iOS 工程師

**Mail:** shinren.pan@gmail.com　　**GitHub:** https://github.com/shinrenpan　　**App Store:** https://apps.apple.com/developer/pan-shinren/id1467353807

**Blog:** https://shinrenpan.github.io　　**YouTube（開發紀錄）:** https://www.youtube.com/@shinrenpan

---

## Summary

**15 年以上** iOS 開發經驗，做過 MFi 硬體、即時通訊、影音串流、金融交易等類型的 App，從純 Objective-C 一路寫到 Swift / SwiftUI。

主要專注在**架構設計**，習慣先把 Apple 官方框架的設計意圖弄清楚，再在這個基礎上設計低耦合、好維護的方案，而不是直接套一個偏離原生的第三方 Framework。依賴管理也是同樣做法：Apple API 能解決的就用原生，減少維護風險與 Binary Size。不特別堅持某一套架構，進新團隊能照現有風格走，現有方案不夠用時才自己設計，MVVMC 就是這樣來的。

做過的 App 類型夠雜，多數常見需求都有實作過的前例，遇到問題時比較快能判斷方向。

工作之外獨立開發並上架三款 App，設計、開發、後端串接到上架維運都是自己來。近期的業餘時間則投入 HL7 FHIR，包含一台以 Swift 實作的 FHIR R4 Server。

---

## 技能

### 程式語言
- **Swift** 3.0 ~ 現在
- **Objective-C** 2009 ~ 現在

### UI
UIKit 與 SwiftUI 都能獨立刻出複雜的自訂介面；兩者混搭是 MVVMC 的基礎，`UIHostingController` 當導航單元、SwiftUI 負責畫面渲染。早期寫過 cocos2d for iPhone，後來延伸到 SpriteKit，UIKit / SwiftUI 做不出來的動畫會改用 SpriteKit。

`UIKit` `SwiftUI` `UIHostingController 混搭` `AutoLayout` `Core Animation` `SpriteKit`

### 架構
主導或參與過多種架構的導入與重構，現有方案不夠用時會自己設計。

`MVC` `MVVM` `Clean Swift` `TCA` `MVVMC（自研）` `@Observable / @MainActor`

### Swift Concurrency
接手既有 Swift 5+ 專案，導入 Swift Concurrency 並重構到 Ready for Swift 6。

`async/await` `@MainActor` `actor` `Sendable` `Task / TaskGroup`

### 網路
以 URLSession 為主，視需求使用 gRPC；Alamofire 等第三方也有實務經驗。

`URLSession` `gRPC (grpc-swift / connect-swift)` `Alamofire`

### 即時通訊
主流協議都在實際專案用過，文字通訊與影音串流都有。

`WebSocket` `XMPP` `MQTT` `SignalR` `Live Streaming (HaishinKit / ijkplayer / ReplayKit)`

### 資料庫
優先用原生方案，主流第三方也用過。

`CoreData` `SwiftData` `KeyChain` `NSKeyedArchiver` `Realm` `fmdb`

### 後端
以 Swift 寫過完整的 HTTP Server（詳見 Projects 的 Siming），另有 Python FastAPI 與 Docker 部署的實作經驗。

`Swift on Server (Hummingbird 2 / SwiftNIO)` `PostgresNIO` `PostgreSQL` `Python FastAPI` `Docker`

### 醫療整合
以自主專案做過端到端的 FHIR 實作：Server 端（Siming）、SMART on FHIR client（Tideng）、TW Core IG 資料模型套件（TWCoreFHIRModels）與掛號 App（FHIRpass）。也了解台灣醫療 IT 的實際狀況，包括 SMART on FHIR 與靜態 Token 之間的取捨。

`FHIR R4` `SMART on FHIR` `TW Core IG` `HAPI FHIR` `Apple FHIRModels` `TWCoreFHIRModels` `ASWebAuthenticationSession`

### 藍芽
以 CoreBluetooth 實作過無伺服器的裝置直連（SideBell 呼叫鈴），早期另有 MFi 外接硬體與 BLE 整合經驗。

`CoreBluetooth` `iBeacon`

### 工具鏈

| 類別 | 工具 |
|------|------|
| 版本控制 | Git |
| 套件管理 | Swift Package Manager、CocoaPods、Carthage |
| Project 管理 | XcodeGen、Tuist |
| CI / CD | Xcode Cloud、Jenkins、Fastlane、Firebase App Distribution |
| 規格驅動開發 | [Spectra](https://github.com/kaochenlong/spectra-app)（SDD）：能力規格與變更提案納入版控，規格先行再實作 |
| AI 協作 | Claude Code（以 CLAUDE.md + Skill 文件約束產出，使其符合專案既有架構） |

---

## 工作經歷

### DRACO EVOLUTION
**資深 iOS 工程師**　　2025/04 ~ 2026/06　　外包結束後接手，擔任公司唯一 iOS 工程師

接手外包 App 後，評估程式碼品質、清償技術債，並主導架構調整。

- **TCA 升級與移除：** 接手時版本為 1.15.2，先逐版升級至 1.22.2。維護與新增 Feature 期間，發現 TCA 內建 Navigation Stack 無法應對 App 非典型 Route 規則，開始著手重構，測試穩定後於 2025/09/18 正式移除。
- **自研 MVVMC 架構（[GitHub](https://github.com/shinrenpan/MVVMC)）：** 移除 TCA 後，SwiftUI 原生 NavigationStack 一樣處理不了複雜的非典型 Route（例如結帳後要同時 dismiss、切 Tab、清 stack），加上不想讓整個 codebase 的架構綁在第三方套件上，決定借鑒 TCA / MVI 的概念，用原生 Swift 自己設計：在 MVVM 之上加一層 HostController（C 層）。M 層管 State / Domain Models / DTOs，VM 層以 `@Observable @MainActor` 單一入口（`doAction`）處理業務邏輯，V 層是零導航邏輯的純 SwiftUI，C 層（`UIHostingController`）擔任唯一 Router，所有導航透過 `AppRouter.shared` 集中管理。後來整理成開源 repo，並附上 MCP Server，讓 Claude Code 在任何專案都能取得規範。
- **Swift 5 → Ready for Swift 6 重構：** 接手時 codebase 是 Swift 5+，陸續導入 `async/await`、`@MainActor`、`actor`、`Sendable`，在移除 TCA、重構 MVVMC 的過程中一併完成 Swift 6 相容遷移。
- **建置 Xcode Cloud CI/CD：** Dev 環境自動分發 TestFlight 內部測試、Production 環境自動分發 TestFlight 外部測試，不需人工介入。
- **App Store 上架（美國）：** 因應 SEC 合規要求僅於美國市場上架；後因 API 停止服務，App 暫時下架。
- **導入 AI 工具鏈（Claude + Skill）：** 建立 `CLAUDE.md` 與多份 Skill 文件（SwiftUI、ViewModel、HostController、Model、Swift Concurrency 等），讓 Claude 依專案架構產出符合規範的 Feature 程式碼。

---

### 皆凱科技
**iOS 工程師**　　2023/09 ~ 2024/09　　三人 iOS 團隊主力，其餘兩位同事分別專責內部 KLine 套件與另一套 VPN App

負責金融交易平台與金田GT（貴金屬交易理財 App）兩套 App 的維護，並參與基於 Tinode 的 IM 軟體開發。

**金融交易 App（[參考影片](https://www.youtube.com/watch?v=4xdZ6mtfEa0)）**

- 導入 XcodeGen 管理 Project，消除多人協作時 `.xcodeproj` 的 Git 衝突。
- 以 SignalR 介接即時報價資料，搭配 `CADisplayLink + RunLoop` 解決 UICollectionView 拖動時 Cell 更新卡頓問題。
- 使用 UICollectionView 全面替代 UITableView，統一列表 UI 實作方式，以利後續支援複雜佈局與更彈性的 Cell 組合；維護與新增公司內部 KLine 套件。
- 撰寫 Script 自動切換 dev / qat / production 環境，實作 App 內即時語系切換。

**金田GT App（[參考影片](https://youtu.be/Rh_pZrOLsh0)）**

- Swift / Objective-C 混編開發，導入 gRPC 介接資料。
- 基於 [Rate Limiting UITableView/UICollectionView Reloads](http://www.enharmonichq.com/rate-limiting-uitableview-and-uicollectionview-reloads/) 的思路，解決高頻 gRPC 資料變動時 reload 過度頻繁的效能問題。
- 實作審核模式下隱藏特定 UI 功能，順利通過 App Store 審查。
- 以 Jenkins + Fastlane 建立 CI/CD，Firebase 分發 dev / qat 測試包。
- 導入 Xcode 15 Asset Symbol Generation；實作 App 與 HTML5 網站雙向互動（JavaScript Bridge）。

**IM 軟體（基於 Tinode）**

- 為大幅客製化 Tinode 預設介面，移除 Storyboard 改以 Hardcoded UI 實作，提升改版彈性。
- 公司沒有 Golang 工程師，為了搞清楚 Server 行為、評估 IM 功能做得到哪裡，自學 Golang 並讀過 Tinode Server 端程式碼。

---

### 恒遠科技
**iOS 工程師**　　2022/04 ~ 2023/07　　獨立負責整個 iOS 專案（[參考影片](https://youtu.be/vgyh0lbtPYY)）

接手大陸同事 Objective-C 專案，主導技術轉型。App 包含短影音、長影音、漫畫、小說、遊戲、直播、聊天等功能。

- **主導 ObjC → Swift 遷移：** 採漸進式策略，新功能一律用 Swift，舊模組逐步重構。
- 導入 XcodeGen 解決 Git Project 衝突；研究 Tuist 並評估兩者差異。
- **重構短影音本地播放架構：** 原架構用 GCDWebServer 架本地伺服器播放下載好的 m3u8，維護成本高。改成自訂 `AVAssetResourceLoaderDelegate`：把 `file://` scheme 換成自訂的 `local://`，AVPlayer 就會把請求交給 Delegate，Delegate 再換回 `file://` 讀本地資料回應，移除 GCDWebServer 依賴，Binary Size 也跟著下降（[參考文章](https://shinrenpan.github.io/2022-07-13/)）。
- 實作漫畫閱讀器、小說閱讀器、遊戲嵌入頁面，三者皆透過 WebView 與 Native 層雙向溝通。
- 導入合作方以 Flutter 開發的直播套件，處理 Flutter module 嵌入 Native 的整合問題，並跨 framework 進行 debug。
- 對接第三方簽名廠商發佈 App（企業內部發佈，繞過 App Store 審核流程）。

---

### 遊戲橘子集團
**iOS 約聘工程師**　　2019/06 ~ 2022/02

**[BeanFun](https://apps.apple.com/tw/app/beanfun/id1108282446) App**

- 與團隊共同導入 Clean Swift 架構，將 Objective-C 模組逐步重構為 Swift。
- BeanFun 大量功能以 WebView 承載，且要支援 Hot Reload，實作 WebView ↔ Native App 的雙向溝通機制，包含 JavaScript Bridge 設計、事件傳遞與頁面狀態同步。

---

### 遊戲橘子集團
**iOS 約聘工程師**　　2018/09 ~ 2019/03　　主力負責 iOS 開發

**In-House 企業管理 App「teamup!」**

橘子集團內部專案管理與簽核平台，支援即時通訊、線上簽核與門禁整合，曾於執行長劉柏園前進南極期間作為遠端管理工具（[參考報導](https://www.bnext.com.tw/article/51537/gamania-teamup)）。

- 針對低頻寬環境優化：以 fmdb 快取 API 資料實現離線使用，實作多層次圖片快取（先顯示縮圖，背景下載原圖再替換），讓 App 在弱網下仍能正常操作。

---

### 緯創軟體
**iOS 工程師**　　2016/08 ~ 2018/03

以緯創身分駐點國泰人壽，是唯一派駐的 iOS 工程師，負責[國泰人壽 App](https://itunes.apple.com/tw/app/id432046643) 的維護。原始專案以 Objective-C 開發，因應國泰內部引入 Swift 的技術決策，負責新功能以 Swift 實作，並逐步推動 Objective-C 模組的重構與過渡。

---

### 和特資訊
**iOS 工程師**　　2016/03 ~ 2016/06

參與新創飯店企業管理 App 開發，供飯店員工進行排班管理、即時回報與打卡簽到。後端選用 SignalR 實作聊天功能，當時業界主流是 XMPP 與 MQTT，SignalR 算少見的選擇，也因此有了 SignalR 的實作經驗。另外實作基於 Core Location 的地點限制打卡。

---

### 互聯網行動科技
**iOS 工程師**　　2015/04 ~ 2016/01

依老闆構想開發購物商城 App，核心概念是讓使用者透過內嵌遊戲（靈感來自 Tap Titans 玩法）獲得虛擬幣或優惠券，再於商城內使用。以 XMPP 實作聊天功能，並用 SpriteKit 開發遊戲模組，這是第一次把遊戲引擎整合進電商 App。

---

### 其他早期經歷（2010 ~ 2015）

| 公司 | 期間 | 主要內容 |
|------|------|----------|
| PiPiMy | 2015/01 ~ 2015/03 | C2C 二手交易 App（Beta） |
| 時間軸科技 | 2012/05 ~ 2014/06 | 套版商城 App 架構設計 / [優惠券 App](https://itunes.apple.com/tw/app/id551945238) |
| JamZoo | 2012/11 ~ 2013/06 | 將「單身銀行」App 聊天機制由 Timer Polling 重構為 MQTT（參考 Facebook 採用 MQTT 的技術決策），解決輪詢造成的卡頓問題；另開發[離線租車 App](https://www.youtube.com/watch?v=aail3KJdb4c)、HTML5 電子書 WebView |
| 汎美達電信 | 2010/09 ~ 2012/02 | [Media Player 互動 App](https://www.youtube.com/watch?v=Unv4XT5EjNI)、[小遊戲](https://www.youtube.com/watch?v=fLPyCJoCQWY)、BLE |
| 旭揚半導體 | 2010/03 ~ 2010/07 | [MFi 外接硬體 App](https://www.youtube.com/watch?v=ZVgwwkCCrUQ)、網路電台、Local 音樂播放 |

---

## Projects

### 已上架 App

**HerbMeet（哈波蜜）**　　[App Store](https://apps.apple.com/tw/app/herbmeet-vegan-restaurant-map/id6787411907)

台灣蔬食餐廳地圖。一間店可以同時掛全素 / 奶素 / 蛋素 / 五辛等多重標記，歇業的店轉灰保留而不刪除。資料的修正要經過多人投票才生效，避免單一帳號改寫店家資訊。後端以 Supabase 承載資料與投票邏輯，繁中英文雙語系，免費使用，僅有「投票權重 +1」的一次性 IAP。

**FoodEntropy（食熵）**　　[App Store](https://apps.apple.com/app/id6793926521) · [GitHub](https://github.com/shinrenpan/FoodEntropy)

食材效期管理 App，持續維護中，是 MVVMC 跑在實際產品上的案例。Widget 直接共用 App 本身的呈現層程式碼，不另外寫一份 UI；資料層是 SwiftData，iCloud 同步做成使用者可自行開關的選項，因此 schema 全程避開 CloudKit 不支援的設計。開發流程採 Spectra 的 SDD：功能先寫成 `openspec/specs/` 下的能力規格，改動先開變更提案，實作完成才歸檔，規格與提案都進版控。

**SideBell（隨身鈴）**　　[App Store](https://apps.apple.com/us/app/sidebell/id6799201744) · [GitHub](https://github.com/shinrenpan/SideBell)

不需要網路的無障礙呼叫鈴。病患端 iPad 按一下，照護者的 iPhone 立即響鈴並唸出需求、持續重複到有人回應，全程透過藍牙直連，無伺服器、無帳號、無訂閱。為 ALS、重度行動障礙或臥床復原者設計。純 SwiftUI + MVVMC 架構，107 個測試，附操作影片與中英文說明文件站。

### 架構與開源

**MVVMC 系列**　　[MVVMC](https://github.com/shinrenpan/MVVMC) · [MVVMR](https://github.com/shinrenpan/MVVMR) · [MVVMC-Skip](https://github.com/shinrenpan/MVVMC-Skip)

工作中設計並實際導入的四層 iOS 架構（詳見上方 DRACO 經歷），整理為開源 repo，附可執行的 Demo 與 MCP Server。

同一套架構後來往兩邊延伸：**MVVMR** 用 Pure SwiftUI 重寫一次，M / VM 一行不改，導航改跑 `NavigationStack` + `@Environment` AppRouter，路由從命令變成值；**MVVMC-Skip** 則透過 Skip.tools 帶上 Android，用 `#if SKIP` 條件編譯替換 C 層，iOS 端零改動。

**WebParser**　　[GitHub](https://github.com/shinrenpan/WebParser)

基於 WKWebView 離屏渲染的網頁解析 Swift Package，針對需要執行 JavaScript 的動態網頁（SPA、動態 DOM）。以泛型 Mapper 提供型別安全的解析介面（JSON → `Decodable`、自訂 Regex 擷取），採用 Swift 6 strict concurrency 與 Swift Testing，GitHub Actions CI，透過 SPM 發佈。

### 醫療 / FHIR

**Siming（司命）**　　[GitHub](https://github.com/shinrenpan/Siming)

以 Swift 寫的 FHIR R4 Server，鎖定小型診所的臨床資料場景並符合 TW Core IG。Hummingbird 2（SwiftNIO）+ PostgresNIO（不使用 ORM）+ Apple FHIRModels，支援 24 種 FHIR R4 資源的 CRUD、search、history、compartment 與 transaction bundle，附內建資源瀏覽器、一行指令的 Docker 部署與 GitHub Actions CI。Terminology 驗證交由選用的 HL7 Validator sidecar，不自行實作。

**Tideng（提燈）**　　[GitHub](https://github.com/shinrenpan/Tideng)

iPad 原生的 SMART on FHIR client，走標準 SMART standalone launch，已在公開沙箱 `launch.smarthealthit.org` 與本專案自帶的 Siming + Keycloak 環境上驗證。實作臨床瀏覽流程所需的資源：`Patient`、`Encounter`、`MedicationRequest`、`Observation`、`Practitioner` / `PractitionerRole`。

**FHIRpass**　　[GitHub](https://github.com/shinrenpan/FHIRpass)

醫療掛號 App MVP，病患端掛號、醫護端處理掛號。設計重點在繞開第三方服務進醫院時的兩個實際障礙：資安防火牆與個資法合規，因此拆成離線 QR、SMART on FHIR 授權（`ASWebAuthenticationSession` + OAuth2 + PKCE，Token 鎖在 Keychain）與 iPad 櫃檯掃碼三條可獨立運作的軌道。iOS、FastAPI、HAPI FHIR 與掃碼前端都是自己做。

**TWCoreFHIRModels**　　[GitHub](https://github.com/shinrenpan/TWCoreFHIRModels)

給台灣 iOS / Swift 開發者用的 TW Core IG 擴充 Swift Package。直接拿 Apple FHIRModels 產出符合衛福部規範的 FHIR 資料時，得自己翻規格、hardcode Profile URL 與 CodeSystem URL、再寫一份必填欄位驗證。這個套件在 `ModelsR4` 之上提供強型別的 `.twCore` namespace API，可以直接操作台灣特定欄位，並用 `validateTWCore()` 驗證 SHALL 必填欄位。

- 強型別 `.twCore` namespace，直接賦值身分證號、Profile 宣告、SHALL 欄位驗證，消除 hardcode URL
- Swift 6.2 strict concurrency、GitHub Actions CI、SPM 發佈

### 早期作品（Objective-C 時期）

2014 ~ 2018 年 Objective-C 時期釋出的開源元件，其中 [`SRPPlayerViewController`](https://github.com/shinrenpan/SRPPlayerViewController)（基於 ijkplayer 的極簡播放器）累積約 30 個 star，其餘見 GitHub。

---

## 學歷

| 學校 / 機構 | 科系 / 課程 | 期間 |
|---|---|---|
| 朝陽科技大學 | 資訊管理系（夜間部） | 2004/09 ~ 2007/01 |
| 資策會數位內容學院 | iOS 開發課程（六個月） | 2009 |

> 結業作品：以 cocos2d for iPhone 開發音樂節奏遊戲《擋十個》，榮獲 **2009 數位內容系列競賽手機遊戲創作組金獎**。結業後與同學接案開發[音樂 App](https://www.youtube.com/watch?v=npV4b-Z9A4w&t=177s)。

**語言：** 中文（母語）　英文（讀寫可應對技術文件）
