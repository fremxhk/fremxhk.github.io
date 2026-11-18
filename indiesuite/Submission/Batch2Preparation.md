# Five-app App Store submission preparation

Status verified 18 November 2026 (Hong Kong). **Preparation only: these five apps have not been submitted to App Review.** The existing VaultGlass, BioPulse Local and ClauseShield submissions are separate. No physical device was accessed for this work.

| App | App Store record | Version / selected build | Status |
| --- | --- | --- | --- |
| DeductGlass | [6835851991](https://appstoreconnect.apple.com/apps/6835851991/distribution/ios/version/inflight) | 1.0.0 / 1, VALID | Prepare for Submission; manual release |
| EchoBrief | [6835852599](https://appstoreconnect.apple.com/apps/6835852599/distribution/ios/version/inflight) | 1.0.0 / 1, VALID | Prepare for Submission; manual release |
| NutriLoupe | [6835853020](https://appstoreconnect.apple.com/apps/6835853020/distribution/ios/version/inflight) | 1.0.0 / 1, VALID | Prepare for Submission; manual release |
| TorqueShield | [6835853579](https://appstoreconnect.apple.com/apps/6835853579/distribution/ios/version/inflight) | 1.0.0 / 1, VALID | Prepare for Submission; manual release |
| RecallGlass | [6835854026](https://appstoreconnect.apple.com/apps/6835854026/distribution/ios/version/inflight) | 1.0.0 / 2, VALID | Prepare for Submission; manual release |

The [development workspace](../Documentation/Workspace.md) and its project-local build/test evidence now reside on the connected Xcode SSD; migration was checksum verified.

## Saved and verified

- Registered explicit App IDs, provisioned distribution signing and associated each app with its own iCloud container. All five selected archives and App Store exports passed package checks, uploaded and processed to VALID. RecallGlass uses build 2 with the fitted cutout-preview correction; the other four use build 1. [Build fingerprints](../Documentation/BuildVerification.md).
- Saved English (US) names, subtitles, descriptions, keywords, categories, copyright, privacy/support/marketing URLs, age declarations, content rights, private review contacts and six-point review notes. All 15 public URLs returned HTTP 200.
- Configured free base apps, US availability, five subscription groups and 15 products. Prices: USD 4.99/month, 29.99/year and 79.99 lifetime. Each annual product has a one-week eligible free trial. Price and country configuration were read back from Apple. Apple-required converted subscription price entries were added for all 175 territories; this does not enable availability outside the US.
- Uploaded 32 native, unresized store screenshots: 16 iPhone captures at 1206 × 2622 and 16 13-inch iPad captures at 2064 × 2752. All are opaque RGB PNGs from passing synthetic-data UI flows; all asset deliveries are COMPLETE. Apple-hosted source checksums and file sizes match all 32 reviewed PNGs.
- Uploaded 15 product review screenshots from actual local StoreKit UI. Each subscription uses its own selected-plan screenshot; each lifetime product shows the separate purchase. All deliveries are COMPLETE.
- Prepared five unsubmitted App Review drafts, each containing its three product versions and subscription group version. Automatic TestFlight notifications are disabled. No tester was asked to use a physical device.
- Saved NutriLoupe’s required medical-device declaration as No for the current consumer-wellness scope; this is not a claim of FDA clearance.
- Saved “Data Not Collected” privacy drafts in the browser. They are not published; publication is a legal attestation and remains an owner decision.

## Passing simulator evidence

- [Five distinct purchase UI methods](../Documentation/Batch2PurchaseResults.md): monthly and annual local purchases, lifetime local purchase, active access, cold relaunch persistence and legal links. No forced Pro entitlement or real payment was used.
- [Nine app/mode pipeline methods across eight apps](../Documentation/Batch2TestResults.md), rerun under Xcode 27.2. Input/PDF ingestion, model-or-validated fallback, persistence, deterministic calculations and PDF exports are covered by the listed assertions.
- [Five studio UI workflows](../Documentation/Batch2UIResults.md), repeated on native phone/tablet capture configurations: 10 passing executions, five distinct methods. Repeats do not increase the unique count.
- The existing [51-method main regression inventory](../Documentation/TestResults.md) remains separately version-qualified; it was not relabeled as a new full regression run.

Functional simulator work used one iPhone 17e running iOS 27.0. Capture-only profiles then ran one at a time, with the prior task-owned simulator shut down before switching. All selected phone and tablet capture cases passed on iOS 27.0. RecallGlass build 2 also passed an additional complete tablet control on iOS 27.2; the case-level report identifies the selected candidate results. Jobs were limited to two; parallel tests and clones were disabled.

## Remaining owner and release decisions

Publish the saved privacy declarations, review the app/product metadata and native screenshots, then authorize the final App Review submission. The app-version review item remains to be attached after required privacy publication. These preparations do not establish production readiness or promise Apple acceptance.

The owner’s physical-device hold remains in force. No physical recording is claimed. Production CloudKit schema deployment/synchronization, actual microphone/transcription and Calendar/Reminders dispatch, printer margins and live App Store transactions remain outside the simulator evidence. Any request from Apple for current-build physical evidence must be answered honestly, without presenting simulator footage as physical evidence.

## Reproducible checks

`python3 Scripts/verify-submission.py` validates all eight metadata sets and 24 product localizations. Archive/export validators accept an explicit app-name list to preserve the first three candidates’ evidence. `Scripts/run-batch2-purchase-qa.sh EXISTING_IOS_27_SIMULATOR` and `Scripts/report-batch2-purchase-results.py RESULT_ROOT` reproduce the scoped purchase checks. `Scripts/capture-batch2-store-assets.sh IPHONE_SIMULATOR IPAD_SIMULATOR` captures the native profiles sequentially. Signing keys, private contacts, IPAs, raw diagnostics and API tokens are excluded from Git.
