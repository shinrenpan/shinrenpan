# 個人簡介（104 / 1111 / Yourator 等）

15 年以上 iOS 開發經驗，主要做架構設計與重構（含自研的 MVVMC 架構），熟悉 Swift / SwiftUI / UIKit，有多次獨立負責整個 iOS 專案的經驗。獨立開發並上架三款 App Store App，近期投入 HL7 FHIR 生態，Server、client 與資料模型套件都自己實作過。

詳細資訊請參考：https://github.com/shinrenpan/shinrenpan/blob/main/Resume_zhTW.md

---

# 自傳（104 / 1111 / Yourator 等）

我有 15 年以上的 iOS 開發經驗，做過 MFi 硬體、即時通訊、影音串流、金融交易等類型的 App，從 Objective-C 時代一路寫到現在的 Swift / SwiftUI。

技術選型上我習慣原生優先，能用 Apple 原生解決的就不隨便引第三方套件，維護成本與 Binary Size 都比較好控制。接手技術債比較重的專案時，這個習慣也讓我能一步步把不必要的依賴拿掉，把架構收回可控的範圍。

架構上我不特別堅持哪一套。做過 Objective-C 到 Swift 的漸進式遷移，也導入過 Clean Swift、TCA；後來 TCA 應付不了專案的導航需求，就自己設計了 MVVMC（已開源：https://github.com/shinrenpan/MVVMC），以 UIHostingController 當導航單元、SwiftUI 負責畫面，另外附了 MCP Server 讓 AI 工具能取得架構規範。

近幾年有幾次是一個人負責整個 iOS 專案：從外包手上接過來、評估程式碼品質、清技術債，到後續持續加新功能，習慣在資源有限的情況下自己把事情推完。

最近的個人專案改用 Spectra 的規格驅動開發（SDD）流程：功能先寫成規格、改動先開變更提案，實作完才歸檔，規格與提案都進版控；Claude Code 則依 CLAUDE.md 與 Skill 文件在這些規格底下產出符合專案架構的程式碼。

另外，近期比較多時間放在 HL7 FHIR 這塊，而且是從頭做到尾：Siming 是用 Swift（Hummingbird 2 / SwiftNIO）寫的 FHIR R4 Server，Tideng 是 iPad 上的 SMART on FHIR client，TWCoreFHIRModels 是衛福部 TW Core IG 的 Swift Package，FHIRpass 則是掛號 App 的 MVP。對台灣醫療 IT 的實際狀況也有一定了解。這部分目前是自主研究累積的，還沒有對應的工作經歷。

工作之外我也獨立開發並上架了三款 App：「哈波蜜」（台灣蔬食餐廳地圖，資料由社群投票維護，Swift 6 + SwiftUI + MapKit，後端用 Supabase）、「食熵」（食材效期管理）和「隨身鈴」（不需網路的藍牙無障礙呼叫鈴）。後兩者用的就是我自己設計的 MVVMC 架構，算是把架構真的放到產品上跑過一輪。

---

# LinkedIn About

15+ years of iOS development across MFi hardware, instant messaging, video streaming and fintech, from Objective-C through to Swift and SwiftUI.

Most of my work is architecture. On my last project I removed TCA once its navigation stack couldn't express the app's routing rules, and replaced it with MVVMC (github.com/shinrenpan/MVVMC), a four-layer design written in plain Swift. That is roughly how I work: figure out what Apple's frameworks were built to do, then stay on that path.

Same rule for dependencies: Apple APIs first, third-party only when there's no reasonable alternative. I've been the sole iOS engineer on a project several times, taking over outsourced codebases and reworking the architecture on my own.

Lately most of my own time has gone into HL7 FHIR, end to end: Siming, a FHIR R4 server written in Swift (Hummingbird 2 / SwiftNIO); Tideng, an iPad SMART on FHIR client; TWCoreFHIRModels, a Swift Package for Taiwan's TW Core IG; and FHIRpass, an appointment app MVP. All personal projects.

I've also shipped three apps to the App Store on my own: HerbMeet (a crowdsourced vegetarian restaurant map for Taiwan, Swift 6 / SwiftUI / MapKit on a Supabase backend), FoodEntropy (food-expiry tracking) and SideBell (an offline Bluetooth call bell for accessibility). The last two run on my own MVVMC architecture — the architecture in a real product rather than a demo.
