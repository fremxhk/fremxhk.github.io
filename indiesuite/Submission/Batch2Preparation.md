# Five-app App Store submission preparation

Status: 17 November 2026. **Preparation in progress; all five remain unsubmitted with manual release selected.** No physical device is being used. All 16 native iPhone store captures and 11 native iPad captures for DeductGlass, EchoBrief, NutriLoupe and TorqueShield are uploaded with COMPLETE delivery. RecallGlass’s tablet workflow is awaiting a focused retest after a rehearsal navigation-bar harness fix; its five tablet screenshots remain pending. No physical device was used.

| App | App Store record | Selected build |
| --- | --- | --- |
| DeductGlass | [6835851991](https://appstoreconnect.apple.com/apps/6835851991/distribution/ios/version/inflight) | 1.0.0 (1), VALID |
| EchoBrief | [6835852599](https://appstoreconnect.apple.com/apps/6835852599/distribution/ios/version/inflight) | 1.0.0 (1), VALID |
| NutriLoupe | [6835853020](https://appstoreconnect.apple.com/apps/6835853020/distribution/ios/version/inflight) | 1.0.0 (1), VALID |
| TorqueShield | [6835853579](https://appstoreconnect.apple.com/apps/6835853579/distribution/ios/version/inflight) | 1.0.0 (1), VALID |
| RecallGlass | [6835854026](https://appstoreconnect.apple.com/apps/6835854026/distribution/ios/version/inflight) | 1.0.0 (1), VALID |

Completed and read back from Apple: English (US) metadata, age declarations, content rights, private review contacts and six-point notes; free base apps and US-only availability; five subscription groups and 15 products. Monthly is USD 4.99, annual USD 29.99 with an eligible one-week trial, and lifetime USD 79.99. All ten subscriptions have Apple-required prices in 175 territories, without enabling non-US availability. All 15 product review screenshot deliveries are COMPLETE. Each unsubmitted review draft contains its three product versions and subscription group version.

All five distribution archives/exports passed package checks and uploaded successfully. [Signed build fingerprints](../Documentation/BuildVerification.md). Each App ID has its own registered iCloud container; production schemas and synchronization are not certified.

[Five target-qualified local purchase methods](../Documentation/Batch2PurchaseResults.md) and the [nine-method eight-app pipeline rerun](../Documentation/Batch2TestResults.md) passed under Xcode 27.2, on one iOS 27.0 iPhone 17e simulator. [Local StoreKit screenshots](../Documentation/Previews/Batch2/Purchases/README.md) demonstrate test transactions and cold relaunch, not live payments. The existing main 51-method regression inventory remains separately version-qualified.

The saved “Data Not Collected” privacy drafts are unpublished. After native asset capture/upload and final validation, privacy publication and final App Review submission remain owner decisions. The physical-device hold remains in force; no physical recording is claimed. Actual audio/calendar/printer behavior, live App Store transactions and production cloud services remain outside these simulator results.

## Native capture evidence in progress

The iPhone capture bundle passed all five workflows. Four tablet workflows have individually verified Passed results in `TestResults/Batch2-Store-Captures-20261117-204958/iPad.xcresult`; that bundle also contains an interrupted RecallGlass attempt, which is not counted as passing. The affected RecallGlass method is being rerun separately. Its unchanged app behavior has passing phone evidence; tablet timer and cutout completion remain pending. [Native captures currently available](../Documentation/Previews/AppStore/Batch2/README.md).
