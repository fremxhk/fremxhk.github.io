# Lightkeeper submission preparation

Updated 2026-10-23. **24 physical-device tests and 100 simulator tests pass. A supplemental physical walkthrough is published; production submission remains on hold for exact-TestFlight integration checks and final purchase evidence.** App Store Connect contains **Lightkeeper: Lantern Puzzles**, app `6825834948`, version 1.0, manual release, Prepare for Submission.

Completed: English listing and review contact; categories and age rating; free base app; nine IAPs and two equal-benefit subscriptions; Apple-localized prices and seven-day trials in 146 storefronts; active paid/free agreements, banking and tax status checked; published App Privacy with owner approval; signed archive validation and upload; nine hosted island packs uploaded and processed; private TestFlight QA group and tester; beta review submitted and waiting for Apple.

The EU is deliberately disabled until DSA trader verification. China mainland and Vietnam are excluded pending game-specific regional licensing. No account agreements were changed. Registered advertising/analytics SDKs are excluded from the shipping binary. Daily beacons and the recurring leaderboard now share 00:00 UTC; personal streaks still use the player's local day. All 100 scheme tests passed before the optional screenshot-capture test was added.

Read `setup-status.json` for exact IDs, evidence and unfinished gates, `TESTFLIGHT.md` for installing the beta, `PRIVACY_AND_RIGHTS_AUDIT.md` for the signed build audit, and `physical-device-qa.md` / `recording-script.md` for remaining device work. Eight native iPhone/iPad listing screenshots and all eleven purchase review screenshots are uploaded; simulator images never constitute physical-device evidence. The app, nine IAP versions, two subscription versions, subscription group, three leaderboard versions and nine pack versions (25 resources) are staged in one unsubmitted production review draft; the final submission remains blocked on exact-TestFlight integration QA and final purchase recording. Season dates must match the eventual launch.

Public pages:
- https://fremxhk.github.io/lightkeeper.html
- https://fremxhk.github.io/lightkeeper-support.html
- https://fremxhk.github.io/lightkeeper-privacy.html
- https://fremxhk.github.io/lightkeeper-terms.html

Private API keys and review contact details are stored outside git. `Tools/inspect_app_store_connect.py` performs authenticated read-only inspection using that private configuration. No production App Review response or production submission has been sent.

See `DEVICE_QA.md` for physical test results and the owner-approved iOS 27.2 RC device. Local StoreKit Test purchases need no authentication; approved TestFlight-copy testing remains a separate gate.

[Physical-device walkthrough](https://fremxhk.github.io/lightkeeper-review/device-walkthrough.html) · [QA results](DEVICE_QA.md).
