# Joe Pan — Senior iOS Engineer

**Email:** shinren.pan@gmail.com　　**GitHub:** https://github.com/shinrenpan　　**Blog:** https://shinrenpan.github.io

---

## Summary

Over **15 years** of hands-on iOS development experience across a wide range of app types — MFi hardware accessories, instant messaging, video streaming, and fintech — participating in every stage of the platform's evolution from pure Objective-C to modern Swift and SwiftUI.

Focused on **architecture design and refactoring**: leading ObjC-to-Swift migrations, designing UIHostingController + SwiftUI hybrid navigation systems, all guided by the principles of maintainability, loose coupling, and full control. Adapts quickly to existing team conventions and designs custom solutions when established patterns fall short.

Follows a **native-first philosophy**: Apple's native APIs are always the first choice; third-party dependencies are introduced only when there is no viable native alternative, keeping maintenance overhead and binary size in check.

Recently established a systematic **AI-assisted development workflow** (Claude + Skill specs), building reusable architecture reference documents that allow AI to generate spec-compliant code aligned with the project's existing conventions, meaningfully shortening feature development cycles.

---

## Skills

### Languages
- **Swift** 3.0 – present
- **Objective-C** 2009 – present

### UI
Proficient in both UIKit and SwiftUI, capable of building complex custom interfaces from scratch. The UIHostingController + SwiftUI hybrid pattern is the current primary architecture. Early study of cocos2d for iPhone established a solid 2D graphics foundation, which carried over into deep familiarity with SpriteKit — used as a fallback for animations and interactions that UIKit and SwiftUI cannot achieve natively.

`UIKit` `SwiftUI` `UIHostingController hybrid` `AutoLayout` `Core Animation` `SpriteKit`

### Architecture
Not tied to a single pattern — prioritises maintainability and team adaptability. Has led or contributed to the adoption and refactoring of multiple architectures; designs custom solutions when standard ones prove inadequate.

`MVC` `MVVM` `Clean Swift` `TCA` `Custom UIHostingController + SwiftUI architecture` `@Observable / @MainActor`

### Networking
URLSession is the default (native-first); gRPC is used where the project requires it. Practical experience with Alamofire and other third-party networking libraries.

`URLSession` `gRPC (grpc-swift / connect-swift)` `Alamofire`

### Real-Time Communication
Hands-on production experience with all major messaging protocols, covering both text-based communication and live video streaming.

`WebSocket` `XMPP` `MQTT` `SignalR` `VoIP` `Live Streaming (HaishinKit / ijkplayer / ReplayKit)`

### Persistence
Native solutions are preferred; major third-party options have also been used in production.

`CoreData` `SwiftData` `Keychain` `NSKeyedArchiver` `Realm` `fmdb`

### Bluetooth
`BLE 4.0` `iBeacon`

### Toolchain

| Category | Tools |
|----------|-------|
| Version Control | Git |
| Package Management | Swift Package Manager, CocoaPods, Carthage |
| Project Management | XcodeGen, Tuist |
| CI / CD | Xcode Cloud, Jenkins, Fastlane, Firebase App Distribution |
| AI Development | Claude (CLAUDE.md + Skill specs for systematic code generation) |

---

## Experience

### DRACO EVOLUTION
**Senior iOS Engineer**　　Apr 2025 – Present　　Took over from an outsourced team; sole iOS engineer at the company

Independently assessed code quality, paid down technical debt, and has been iterating on the product continuously since handover.

- **TCA upgrade and removal:** Inherited the project at TCA 1.15.2 and upgraded incrementally to 1.22.2 (1.18.0 → 1.19.1 → 1.20.2 → 1.21.1 → 1.22.1 → 1.22.2). During routine maintenance and feature development, identified that TCA's built-in Navigation Stack could not accommodate the app's non-standard routing requirements, prompting a gradual architectural rewrite that went live on 18 Sep 2025.
- **Custom UIHostingController + SwiftUI navigation architecture:** `UIHostingController` serves as the navigation unit while SwiftUI handles rendering. Each feature is owned by a `FeatureHostController` that holds the ViewModel; routing logic stays in the host layer and SwiftUI views remain free of UIKit dependencies, achieving loose coupling and high maintainability. The pattern was codified into internal Skill documents.
- **Xcode Cloud CI/CD pipeline:** Dev builds distribute automatically to TestFlight internal testers; production builds distribute to TestFlight external testers — fully automated, no manual steps required.
- **AI-assisted development workflow (Claude + Skill):** Authored `CLAUDE.md` and a suite of Skill documents (SwiftUI, ViewModel, HostController, Model, Swift Concurrency, etc.) so that Claude generates feature code that conforms to the project's existing architecture, significantly reducing time-to-feature.

---

### Evervictory Technology
**iOS Engineer**　　Sep 2023 – Sep 2024　　Lead developer in a 3-person iOS team; the other two focused on an in-house K-Line library and a separate VPN app

Primary maintainer of a fintech trading platform and [JinTian GT](https://apps.apple.com/tw/app/id6467499244) (a precious-metals trading app), plus contributions to an in-house IM client built on Tinode.

**Fintech Trading App ([demo](https://www.youtube.com/watch?v=4xdZ6mtfEa0))**

- Introduced XcodeGen to eliminate persistent `.xcodeproj` merge conflicts in a multi-developer workflow.
- Integrated SignalR for real-time quote streaming; resolved UICollectionView cell-update jank during scroll using `CADisplayLink + RunLoop`.
- Replaced UITableView with UICollectionView across the codebase to enable richer layouts and more flexible cell composition; maintained and extended the in-house K-Line charting library.
- Wrote shell scripts to switch between dev / QAT / production environments; implemented in-app live language switching.

**[JinTian GT](https://apps.apple.com/tw/app/id6467499244) App ([demo](https://youtu.be/Rh_pZrOLsh0))**

- Swift / Objective-C mixed-language development; integrated gRPC for data transport.
- Applied the [Rate Limiting UITableView/UICollectionView Reloads](http://www.enharmonichq.com/rate-limiting-uitableview-and-uicollectionview-reloads/) technique to throttle excessive reloads triggered by high-frequency gRPC updates.
- Implemented a review-mode UI-hiding mechanism to pass App Store review.
- Built a CI/CD pipeline with Jenkins + Fastlane; used Firebase App Distribution for dev / QAT builds.
- Adopted Xcode 15 asset symbol generation; built a JavaScript bridge for bidirectional HTML5 ↔ native communication.

**IM Client (Tinode-based)**

- Removed Storyboard in favour of fully programmatic UI to enable deep customisation of Tinode's default interface.
- With no Golang engineer on the team, self-taught Go and read through the Tinode server codebase to understand server behaviour and accurately define the boundaries of IM feature development.

---

### Heng Yuan Technology Co., Ltd.
**iOS Engineer**　　Apr 2022 – Jul 2023　　Sole iOS engineer on the project ([demo](https://youtu.be/vgyh0lbtPYY))

Took over an Objective-C codebase and led the technical modernisation of an app covering short video, long video, comics, novels, games, live streaming, and chat.

- **Led ObjC → Swift migration:** Defined a gradual strategy — all new features written in Swift, legacy modules refactored incrementally.
- Introduced XcodeGen to eliminate Git project-file conflicts; researched Tuist and evaluated both tools.
- **Refactored local HLS playback architecture:** The original approach downloaded m3u8 files locally and served them through GCDWebServer — high maintenance cost. Replaced with a custom `AVAssetResourceLoaderDelegate`: substitutes `file://` with a custom `local://` scheme so AVPlayer delegates the request to the loader, which swaps back to `file://` and reads the local data. Removed the GCDWebServer dependency and reduced binary size ([reference article](https://shinrenpan.github.io/2022-07-13/)).
- Built comic reader, novel reader, and embedded game pages — all using WebView with bidirectional native communication.
- Integrated a live-streaming SDK written in Flutter, resolving Flutter module embedding issues and debugging across framework boundaries.
- Coordinated with a third-party signing vendor for enterprise distribution outside the App Store.

---

### Gamania Group
**iOS Contract Engineer**　　Jun 2019 – Feb 2022

**[BeanFun](https://apps.apple.com/tw/app/beanfun/id1108282446) App**

- Collaborated with the team to introduce Clean Swift architecture, progressively migrating Objective-C modules to Swift.
- BeanFun loads the majority of its features in WebViews and requires hot-reload support; implemented deep WebView ↔ native bidirectional communication covering JavaScript bridge design, event propagation, and page state synchronisation.

---

### Gamania Group
**iOS Contract Engineer**　　Sep 2018 – Mar 2019　　Lead iOS developer

**In-House Enterprise App "teamup!"**

Internal project management and approval platform supporting instant messaging, digital sign-off, and access control. Used by Gamania's CEO during an Antarctic expedition as a remote management tool ([press coverage](https://www.bnext.com.tw/article/51537/gamania-teamup)).

- Optimised for low-bandwidth conditions: cached API responses with fmdb for offline use; implemented multi-tier image caching (thumbnail-first display, background download and swap to full resolution) to keep the app functional on slow connections.

---

### Wistron ITS
**iOS Engineer**　　Aug 2016 – Mar 2018　　On-site at Cathay Life Insurance

Primary maintainer of the [Cathay Life Insurance](https://itunes.apple.com/tw/app/id432046643) app. The codebase was Objective-C; following Cathay's internal decision to adopt Swift, took responsibility for implementing new features in Swift and progressively migrating legacy Objective-C modules.

---

### Hoter Information
**iOS Engineer**　　Mar 2016 – Jun 2016

Developed an in-house hotel workforce management app for staff scheduling, real-time reporting, and check-in. The backend chose SignalR for the chat feature — an uncommon choice at a time when XMPP and MQTT dominated the space — providing first-hand experience with the SignalR protocol. Also implemented geofenced check-in using Core Location.

---

### Internet Mobile Technology
**iOS Engineer**　　Apr 2015 – Jan 2016

Built a shopping app centred on a gamification concept inspired by Tap Titans: users earn virtual currency or discount coupons through in-app gameplay, redeemable in the store. Implemented chat using XMPP and built the game module with SpriteKit — the first experience integrating a game engine into an e-commerce app.

---

### Earlier Experience (2010 – 2015)

| Company | Period | Key Work |
|---------|--------|----------|
| PiPiMy | Jan 2015 – Mar 2015 | C2C second-hand trading app (Beta) |
| Timeline Technology | May 2012 – Jun 2014 | Template-based storefront app framework / [coupon app](https://itunes.apple.com/tw/app/id551945238) |
| JamZoo | Nov 2012 – Jun 2013 | Migrated "Single Bank" app chat from timer polling to MQTT (following Facebook's adoption of MQTT), resolving lag; built [offline-capable car rental app](https://www.youtube.com/watch?v=aail3KJdb4c) and HTML5 e-book WebView |
| Viamedia Mobile Corporation | Sep 2010 – Feb 2012 | [Media Player interactive app](https://www.youtube.com/watch?v=Unv4XT5EjNI), [mini-games](https://www.youtube.com/watch?v=fLPyCJoCQWY), BLE |
| Sunplus Semiconductor | Mar 2010 – Jul 2010 | [MFi hardware accessory app](https://www.youtube.com/watch?v=ZVgwwkCCrUQ), internet radio, local music playback |

---

## Education

| Institution | Programme | Period |
|---|---|---|
| Chaoyang University of Technology | Information Management (evening programme) | Sep 2004 – Jan 2007 |
| Kao Yuan University (5-year) | Electronic Engineering | — |
| Institute for Information Industry | iOS Development (6-month programme) | 2009 |

> Graduation project: developed rhythm game *Block Ten* using cocos2d for iPhone, winning **Gold Award at the 2009 Digital Content Creation Competition (Mobile Game category)**. After graduating, contracted with classmates to build a [music app](https://www.youtube.com/watch?v=npV4b-Z9A4w&t=177s).

**Languages:** Mandarin Chinese (native)　English (technical reading and writing)
