# Five-app App Store submission preparation

Status: 18 November 2026 (Hong Kong). **Preparation in progress; all five remain unsubmitted with manual release selected.** No physical device is being used. All 16 native iPhone store captures and 11 native iPad captures for DeductGlass, EchoBrief, NutriLoupe and TorqueShield are uploaded with COMPLETE delivery. RecallGlass’s tablet workflow is awaiting a focused retest after a rehearsal navigation-bar harness fix; its five tablet screenshots remain pending. No physical device was used.

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

## Final validator and simulator-host gate — 17 November 2026

Apple's app-version validator now reports unpublished app-privacy details for all five apps. RecallGlass additionally requires its 13-inch iPad screenshot set. NutriLoupe's required regulated-medical-device declaration was saved as No and its medical-declaration validation error cleared. This records its current consumer-wellness purpose; it is not a claim of FDA review or clearance. See [Apple's declaration requirements](https://developer.apple.com/help/app-store-connect/manage-app-information/declare-regulated-medical-device-status) and [FDA general-wellness guidance](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/general-wellness-policy-low-risk-devices).

The remaining RecallGlass tablet retest is **blocked before the XCTest runner establishes its connection**. The workspace, archives and test evidence have moved to the connected Xcode SSD after full content, symlink, permission and Git verification. Internal free space measured 16.88 GiB at migration completion; the earlier insufficient-space error is no longer the current gate.

The first SSD retry booted the same dedicated iPad but timed out reapplying its appearance. A subsequent run reused that already configured simulator and its unchanged installed build. `TestResults/Recall-iPad-SSD-20261117-234744/iPad.xcresult` ended on 18 November with “Test crashed with signal kill before establishing connection.” It records zero passes and one runner error; no app method began. The earlier pre-migration stalled-wait runner failure is retained separately.

The host's observed one-minute load average returned to approximately 730, and a resource check found five other projects' Xcode builds and five other booted simulators. Host resource pressure is a possible contributor, not a proven cause of the runner termination. The owner has been asked to pause those other jobs. This task's capture simulator was shut down; no additional test was launched. The remaining step is the complete RecallGlass tablet workflow on a healthy host, followed by native screenshot review/upload and validator readback. No physical device is needed.

Latest passing evidence: five local-purchase UI methods; nine pipeline methods across eight apps; all five native iPhone capture workflows; four individually verified tablet workflows. RecallGlass tablet timer/cutout completion and its five tablet captures remain pending. Canceled or unstarted attempts are not counted as passes. The saved privacy drafts remain unpublished and no new app version has been submitted.

The [development workspace](../Documentation/Workspace.md) has moved to the connected Xcode SSD after checksum verification. The SSD retry ended at runner startup with no passing app method; the next retry awaits adequate host resources.
