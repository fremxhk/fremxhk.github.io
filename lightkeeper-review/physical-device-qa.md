# Release evidence and submission gates

All unchecked gates remain pending. Simulator tests are useful but do not satisfy physical-device QA. Record tester/date/device/OS/build/result/evidence privately for each run. Do not fill PASS until observed.

| Gate | Status | Required evidence |
|---|---|---|
| Latest-public-OS physical launch and complete user flow | NOT TESTED | Physical recording from Home Screen, exact build |
| iOS 26 deployment target / Swift 6.2 compiler | NOT VERIFIED | Build/test logs on supported SDK/toolchain |
| Xcode 27 / Swift 6.4 | Simulator previously passed | Re-run release candidate; preserve logs |
| iPhone 12-class cold puzzle launch <2 seconds | NOT TESTED | Measured physical launch trace |
| iPad, landscape/live resize, Dynamic Type, VoiceOver, contrast/reduce motion | NOT TESTED on devices | Accessibility/layout checklist and evidence |
| Tutorial 0/1/2, solve, undo, hint, no-oil and interrupted run | NOT TESTED on devices | Steps/results, relaunch persistence |
| Sandbox every visible SKU / pending / cancel / restore / revoke | NOT TESTED live | TestFlight StoreKit evidence; no duplicate grants |
| Subscription monthly/yearly/trial and expiry | NOT TESTED live | Benefits, renewal copy, restore and entitlement evidence |
| Two-device signed GameSave and conflict choice | NOT TESTED | Matching save and no wallet duplication |
| Production Game Center scores | Draft boards created; NOT DEVICE TESTED | Auth denial/success and leaderboard results |
| Nine Apple-hosted island packs | NOT UPLOADED/VERIFIED | Install, retry, offline, integrity and cache checks |
| Duet second-device round trip | NOT TESTED on devices | Link open, placements, stats and invalid-link handling |
| Widget, notifications and Live Activities | NOT TESTED on devices | Permission denied/allowed; lock-screen behavior |
| Daily boundary, time zone, streak repair, season dates | Requires release check | Correct upcoming content, real timers, no expired-pass sale |
| Signed archive privacy report / SDK license and asset audit | NOT VERIFIED | Archive report; privacy-label answers; rights inventory |
| Actual screenshots for all required device sizes | PENDING | Current-build screenshots in use |
| Reviewer-accessible physical recording URL | PENDING | Playback without login, no private account data |
| Account, IAPs, agreements, age rating and review contact | Partially configured; legal/privacy/release checks pending | ASC review of configured app record |

Known content: 100 campaign levels committed, first 27 bundled; later islands require nine Apple-hosted packs. Current season begins 2026-10-19 for 28 days; refresh for launch. Ads/analytics SDKs remain inactive. `starter_island` must stay hidden pending a defined benefit. Do not mark a release ready while these content/service gates are unresolved.

Before uploading: run the full scheme tests and content verification described in the repository HANDOFF.md, archive Release with the correct team, validate extensions/capabilities and privacy manifests, and distribute internally via TestFlight. Submit only after this table is complete and the owner authorizes the final submission.
