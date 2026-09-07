<h1 align="left">Hi, I'm Joe Pan</h1>
<h3 align="left">Senior iOS Engineer · 15+ Years · Taiwan</h3>

<p align="left">
  <a href="https://apps.apple.com/developer/pan-shinren/id1467353807">App Store</a> &nbsp;·&nbsp;
  <a href="https://shinrenpan.github.io">Blog</a> &nbsp;·&nbsp;
  <a href="https://www.youtube.com/@shinrenpan">YouTube</a> &nbsp;·&nbsp;
  <a href="Resume_zhTW.md">中文履歷</a> &nbsp;·&nbsp;
  <a href="Resume_en.md">English Resume</a> &nbsp;·&nbsp;
  <a href="https://linkedin.com/in/shinrenpan">LinkedIn</a>
</p>

iOS developer. Most of my work is **architecture**, built on Apple's own frameworks: UIKit, SwiftUI, Swift Concurrency. Native-first for both API choices and dependencies. When the standard patterns aren't enough, I write my own; MVVMC below is the result.

---

### On the App Store

**[HerbMeet](https://apps.apple.com/tw/app/herbmeet-vegan-restaurant-map/id6787411907)** — A vegetarian restaurant map for Taiwan. Multi-tag classification, community voting on corrections, closed venues kept rather than deleted. SwiftUI on a Supabase backend.

**[FoodEntropy](https://apps.apple.com/app/id6793926521)** · [GitHub](https://github.com/shinrenpan/FoodEntropy) — A food-expiry tracking app. SwiftUI over a UIKit Router via HostControllers, SwiftData with opt-in CloudKit sync, a WidgetKit widget sharing the app's own presentation code. MVVMC running in a shipped product.

**[SideBell](https://apps.apple.com/us/app/sidebell/id6799201744)** · [GitHub](https://github.com/shinrenpan/SideBell) — An accessible call bell that works without the internet. One tap on the patient's iPad, the caregiver's iPhone raises an alarm and says what is needed — over Bluetooth, no server, no account.

---

### Open Source

**[MVVMC](https://github.com/shinrenpan/MVVMC)** — A four-layer iOS architecture (M / VM / V / C) for SwiftUI + UIKit hybrid apps. `UIHostingController` is the navigation unit and all routing goes through `AppRouter.shared`, so SwiftUI views carry no navigation logic. Also reimplemented in pure SwiftUI ([MVVMR](https://github.com/shinrenpan/MVVMR)) and carried to Android via Skip ([MVVMC-Skip](https://github.com/shinrenpan/MVVMC-Skip)).

**[Siming](https://github.com/shinrenpan/Siming)** — A FHIR R4 server written in Swift. Hummingbird 2 (SwiftNIO) + PostgresNIO, no ORM. 24 resource types with CRUD, search, history, compartment and transaction bundle; TW Core IG compliant, one-command Docker deployment.

**[Tideng](https://github.com/shinrenpan/Tideng)** — An iPad-native SMART on FHIR client. Connects to any FHIR R4 server supporting SMART standalone launch, including the public sandbox, and reads clinical data.

Also: **[TWCoreFHIRModels](https://github.com/shinrenpan/TWCoreFHIRModels)** (TW Core IG extensions for Apple FHIRModels) · **[FHIRpass](https://github.com/shinrenpan/FHIRpass)** (healthcare appointment MVP) · **[WebParser](https://github.com/shinrenpan/WebParser)** (WKWebView-based web parsing)

---

<p align="left">
  <img src="https://komarev.com/ghpvc/?username=shinrenpan&label=Profile%20views&color=0e75b6&style=flat" alt="shinrenpan" />
</p>

<br>

<p>
  <a href="https://www.buymeacoffee.com/shinrenpan">
    <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="50" width="210" alt="Buy Me a Coffee" />
  </a>
</p>
