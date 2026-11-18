# Five-app App Store submission preparation

Status verified 18 November 2026 (Hong Kong). **Preparation only: these five apps have not been submitted to App Review.** The existing VaultGlass, BioPulse Local and ClauseShield submissions are separate.

| App | App Store record | Version / selected build | Status |
| --- | --- | --- | --- |
| DeductGlass | [6835851991](https://appstoreconnect.apple.com/apps/6835851991/distribution/ios/version/inflight) | 1.0.0 / 2, VALID | Prepare for Submission; manual release |
| EchoBrief | [6835852599](https://appstoreconnect.apple.com/apps/6835852599/distribution/ios/version/inflight) | 1.0.0 / 2, VALID | Prepare for Submission; manual release |
| NutriLoupe | [6835853020](https://appstoreconnect.apple.com/apps/6835853020/distribution/ios/version/inflight) | 1.0.0 / 2, VALID | Prepare for Submission; manual release |
| TorqueShield | [6835853579](https://appstoreconnect.apple.com/apps/6835853579/distribution/ios/version/inflight) | 1.0.0 / 2, VALID | Prepare for Submission; manual release |
| RecallGlass | [6835854026](https://appstoreconnect.apple.com/apps/6835854026/distribution/ios/version/inflight) | 1.0.0 / 3, VALID | Prepare for Submission; manual release |

The current replacement candidates are validated, uploaded, processed to VALID and selected. They include the durable CloudKit cache correction; TorqueShield also preserves quoted service names, prices and safety categories and displays readable decision labels. Earlier candidates remain preserved privately.

The [development workspace](../Documentation/Workspace.md) and its project-local build/test evidence now reside on the connected Xcode SSD; migration was checksum verified.

## Saved and verified

- Registered explicit App IDs, provisioned signing and associated each app with its own private iCloud container. All five current archives and production exports passed package checks; four build 2 candidates and RecallGlass build 3 are processed and selected. [Build fingerprints](../Documentation/BuildVerification.md).
- Saved English (US) names, subtitles, descriptions, keywords, categories, copyright, privacy/support/marketing URLs, age declarations, content rights, private review contacts and six-point review notes. All 15 public URLs returned HTTP 200.
- Configured free base apps, US availability, five subscription groups and 15 products. Prices: USD 4.99/month, 29.99/year and 79.99 lifetime. Each annual product has a one-week eligible free trial. Price and country configuration were read back from Apple. Apple-required converted subscription price entries were added for all 175 territories; this does not enable availability outside the US.
- Uploaded the 32 reviewed current native screenshots: 16 phone captures at 1206 × 2622 and 16 tablet captures at 2064 × 2752. All are opaque RGB PNGs; all deliveries are COMPLETE, and Apple source checksums/file sizes match every reviewed file.
- Uploaded 15 product review screenshots from actual local StoreKit UI. Each subscription uses its own selected-plan screenshot; each lifetime product shows the separate purchase. All deliveries are COMPLETE.
- Prepared five unsubmitted App Review drafts, each containing its three product versions and subscription group version. Automatic TestFlight notifications are disabled. Five internal-only groups, the designated tester membership and current build assignments are verified; all five builds are IN_BETA_TESTING.
- Saved NutriLoupe’s required medical-device declaration as No for the current consumer-wellness scope; this is not a claim of FDA clearance.
- Saved “Data Not Collected” privacy drafts in the browser. They are not published; publication is a legal attestation and remains an owner decision.

## New cloud and repair checks

- [Twenty app-qualified offline storage methods](../Documentation/CloudStorageResults.md) passed across all five app hosts.
- [Production CloudKit schemas](../Documentation/CloudKitDeployment.md) are deployed and read back for all five apps.
- [Five authenticated production service preflights](../Documentation/ProductionServiceResults.md) passed across all 13 record types, including create/read/indexed query/update/delete and isolated-zone cleanup.
- [Two repair grounding regression methods](../Documentation/RepairGroundingResults.md) passed. All five normal durable-storage UI flows passed on both native profiles; a later readable repair-label refinement also passed on each profile.
- The separate automatic synchronization check needs an unlocked Mac session and is left until the remaining independent preparation is finished.

## Passing simulator evidence

- [Five distinct purchase UI methods](../Documentation/Batch2PurchaseResults.md): monthly and annual local purchases, lifetime local purchase, active access, cold relaunch persistence and legal links. No forced Pro entitlement or real payment was used.
- [Nine app/mode pipeline methods across eight apps](../Documentation/Batch2TestResults.md), rerun under Xcode 27.2. Input/PDF ingestion, model-or-validated fallback, persistence, deterministic calculations and PDF exports are covered by the listed assertions.
- [Five studio UI workflows](../Documentation/Batch2UIResults.md), repeated on native phone/tablet capture configurations: 10 passing executions, five distinct methods. Repeats do not increase the unique count.
- The existing [51-method main regression inventory](../Documentation/TestResults.md) remains separately version-qualified; it was not relabeled as a new full regression run.

Functional simulator work used one iPhone 17e running iOS 27.0. Capture-only profiles then ran one at a time, with the prior task-owned simulator shut down before switching. All selected phone and tablet capture cases passed on iOS 27.0. RecallGlass build 2 also passed an additional complete tablet control on iOS 27.2; the case-level report identifies the selected candidate results. Jobs were limited to two; parallel tests and clones were disabled.

## Remaining owner and release decisions

The independent preparation is complete. The saved privacy answers need the owner's publication attestation, and the final native automatic-synchronization checks need an unlocked Mac session. The app-version review item is attached after privacy publication. The five drafts remain unsubmitted with manual release; final App Review submission is a separate owner action.

Automatic CloudKit synchronization is reported separately from the passing service/API checks. Simulator and service evidence are scoped to the operations actually executed; a service pass is not a claim that every platform-specific interaction was exercised.

## Reproducible checks

`python3 Scripts/verify-submission.py` validates all eight metadata sets and 24 product localizations. Archive/export validators accept an explicit app-name list to preserve the first three candidates’ evidence. `Scripts/run-batch2-purchase-qa.sh EXISTING_IOS_27_SIMULATOR` and `Scripts/report-batch2-purchase-results.py RESULT_ROOT` reproduce the scoped purchase checks. `Scripts/capture-batch2-store-assets.sh IPHONE_SIMULATOR IPAD_SIMULATOR` captures the native profiles sequentially. Signing keys, private contacts, IPAs, raw diagnostics and API tokens are excluded from Git.
