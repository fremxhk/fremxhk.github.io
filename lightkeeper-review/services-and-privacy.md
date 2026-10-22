# Service inventory and privacy reconciliation

Snapshot: 2026-10-23. Signed archive audited; App Privacy published with owner approval. "Not linked" and "not collected" are Apple definitions to assess against actual data handling, not assumptions based on local storage.

| Service | Current use | Data / release action |
|---|---|---|
| Local Foundation/SwiftUI/Canvas | Core puzzles, progress, economy | Device save and purchase delivery IDs; no custom server |
| StoreKit 2 / App Store | Optional purchases and subscriptions | Apple verified transaction/entitlement data; configure live products and review purchase-history disclosure |
| GameKit / Game Center | Optional sign-in and leaderboard adapter | Player identity/scores handled by Apple; draft boards created; production release/device verification pending |
| GameSave / iCloud | Optional whole-save sync | Save includes progress, wallet and receipt delivery records; signed two-device verification pending |
| Background Assets | Apple-hosted additional islands | Nine managed packs uploaded and processed COMPLETE; physical-device delivery verification pending |
| WidgetKit / ActivityKit / App Intents | Local widget, activity and deep links | App Group beacon projection; no developer push server |
| UserNotifications | Opt-in local reminder | Permission and local schedule; no remote notification backend |
| System share sheet / universal URL handling | Duet exchange | Seed, placements, moves, elapsed time; chosen recipient/messaging provider may retain link |
| AppLovin MAX 13.6.4 | Dependency only, inactive | Registered in SPM but not linked into the shipping archive; not initialized/called |
| TelemetryDeck 2.14.2 | Dependency only, inactive | Registered in SPM but not linked into the shipping archive; no reporting |
| AdMob / Mintegral / Unity mediation | Not integrated | Do not list as active processors |
| Foundation Models / attribution | Stubbed, not called | No AI request/attribution registration in current flow |
| GitHub Pages | Public policy/support pages | Host may process technical requests; pages add no trackers |
| Email support | User-initiated support | Address, message and attachments via email provider |

Current app manifest declares tracking false, Gameplay Content, User ID and Purchase History linked for app functionality, and required-reason uses for UserDefaults (CA92.1), file timestamps (C617.1) and system boot time (35F9.1). Validate the actual accessed APIs, entitlement behavior, linked SDK manifests and final privacy report; do not copy these declarations blindly into App Privacy. No ATT request is made in the current app flow.

Retain an asset provenance inventory for artwork, typefaces, music and generated puzzles. Include runtime SDK license notices where required by their licenses. Test-only dependencies such as swift-snapshot-testing are not customer-facing services. Do not state that all third-party licensing is cleared until the final archive audit is complete.
