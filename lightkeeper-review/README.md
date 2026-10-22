# Lightkeeper submission preparation

Updated 2026-10-23. **Production submission remains on hold for physical-device QA and recording.** App Store Connect contains **Lightkeeper: Lantern Puzzles**, app `6825834948`, version 1.0, manual release, Prepare for Submission.

Completed: English listing and review contact; categories and age rating; free base app; nine IAPs and two equal-benefit subscriptions; Apple-localized prices and seven-day trials in 146 storefronts; active paid/free agreements, banking and tax status checked; published App Privacy with owner approval; signed archive validation and upload; nine hosted island packs uploaded and processed; private TestFlight QA group and tester; beta review submitted and waiting for Apple.

The EU is deliberately disabled until DSA trader verification. China mainland and Vietnam are excluded pending game-specific regional licensing. No account agreements were changed. Registered advertising/analytics SDKs are excluded from the shipping binary. Daily beacons and the recurring leaderboard now share 00:00 UTC; personal streaks still use the player's local day. All 100 scheme tests passed before the optional screenshot-capture test was added.

Read `setup-status.json` for exact IDs, evidence and unfinished gates, `TESTFLIGHT.md` for installing the beta, `PRIVACY_AND_RIGHTS_AUDIT.md` for the signed build audit, and `physical-device-qa.md` / `recording-script.md` for remaining device work. Eight native iPhone/iPad listing screenshots and all eleven purchase review screenshots are uploaded; simulator images never constitute physical-device evidence. A production review draft is being staged; the final submission remains blocked on physical QA and recording. Season dates must match the eventual launch.

Public pages:
- https://fremxhk.github.io/lightkeeper.html
- https://fremxhk.github.io/lightkeeper-support.html
- https://fremxhk.github.io/lightkeeper-privacy.html
- https://fremxhk.github.io/lightkeeper-terms.html

Private API keys and review contact details are stored outside git. `Tools/inspect_app_store_connect.py` performs authenticated read-only inspection using that private configuration. No production App Review response or production submission has been sent.
