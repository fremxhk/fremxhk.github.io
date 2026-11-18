# Five-app submission check inventory

Checkpoint: 18 November 2026. DeductGlass, EchoBrief, NutriLoupe and TorqueShield 1.0.0 (2), and RecallGlass 1.0.0 (3), are validated uploads selected in unsubmitted, manual-release drafts. Their designated internal TestFlight assignments are IN_BETA_TESTING. Production exports were built from clean source `99c37a4`.

This inventory separates current source/runtime checks, service checks and retained earlier evidence. Repeated methods and API operations are not combined into an inflated grand total.

## Current offline storage — 20 target-qualified methods passed

Each of `DeductGlassCloudReadinessTests`, `EchoBriefCloudReadinessTests`, `NutriLoupeCloudReadinessTests`, `TorqueShieldCloudReadinessTests` and `RecallGlassCloudReadinessTests` passed these four `CloudReadinessTests` methods:

1. `test01CloudKitModelConstraintsAndManifest()` — actual model compatibility and cloud-configured store load.
2. `test02SQLiteDurabilityRelationshipsAttachmentsAndCascade()` — disk save/reopen, values, inverse relationships, 512 KiB receipt preservation and cascade deletion.
3. `test03SignedOutFallbackUsesDurableLocalStore()` — real signed-out account status and a durable factory-created cache.
4. `test04LegacyLocalStoreAdoptsCloudCacheWithoutLosingRecords()` — preserve existing local records at the adopted store URL.

Four shared method bodies ran in five actual app hosts on one iOS 27.0 simulator; zero failures or skips in the selected bundles. [Full storage evidence](CloudStorageResults.md).

## Current interactive flows — five methods passed on both profiles

- `Batch2StudioFlowTests/test01DeductReceiptVerificationAndBinder()`
- `Batch2StudioFlowTests/test02EchoBriefCommitmentReviewAndExport()`
- `Batch2StudioFlowTests/test03NutriIngredientJournalAndAssociations()`
- `Batch2StudioFlowTests/test04TorqueEstimateDecisionAndLeaseWorkspace()`
- `Batch2StudioFlowTests/test05RecallStudyAndSpeechPrintStudio()`

The clean suite passed all 10 executions on iPhone 17 and 13-inch iPad, iOS 27.0. TorqueShield's readable-label update passed its same flow again on each profile. The selected case matrix still represents five distinct methods, with normal durable storage, empty launch arguments and no forced Pro access. The fitted first cue-card sheet is asserted on both profiles. [Exact assertions and selected result/source provenance](Batch2UIResults.md).

## Current repair regressions — two selected methods passed

- `SequentialWorkspaceQASuite/test10_RepairGenerationPreservesQuotedFactsAndSafetyTriage()` — reject altered service names, safety categories, prices, source lines and omitted items; retain a fully grounded generated note.
- `SequentialWorkspaceQASuite/test07_TorqueShield_VINCheckDigitAndEstimateRedliner()` — real import, source facts/safety, relationships, VIN/lease bounds, PDF and sequential smoke pipeline.

The end-to-end method is a rerun of an existing method; it is not counted as an additional distinct test when comparing with the earlier pipeline inventory. [Repair regression evidence](RepairGroundingResults.md).

## Authenticated CloudKit checks

| Check | App-qualified result |
| --- | --- |
| Apple schema dry run from actual model classes | All five passed |
| Real development schema initialization | All five passed |
| Production schema deployment and exported readback | All five confirmed; 13 application record types |
| Production create/direct read/indexed query/update/delete and cleanup | All five passed; all 13 record types checked |
| Automatic export, independent-store import, updates, receipt asset and deletion propagation | Pending an unlocked Mac session; not counted as passed |

The server preflights used signed Mac Catalyst clients in the Production environment and deleted their own synthetic zones. These are separate from iOS distribution-package runtime evidence. [Schemas](CloudKitDeployment.md) · [Production service evidence and pending automatic-sync scope](ProductionServiceResults.md).

## Package, asset and metadata checks passed

- All five intended-app-only archives: exact bundle/version/build/minimum OS, deep/strict signatures, privacy resources, correct cloud containers, no private signing keys or Debug QA launch flags.
- All five production IPAs: verified signatures, debugging disabled, production APNs/iCloud entitlements; speech permissions/linkage present only where used. [Local export fingerprints](BuildVerification.md).
- All five Apple uploads processed to VALID, selected at version 1.0.0 with manual release; current internal tester/group/build assignments read back.
- All 32 current native store PNGs: original dimensions, opaque RGB, individual Passed cases and visual review; Apple source checksums and file sizes match every file, with COMPLETE deliveries.
- All 15 product review images: COMPLETE deliveries, correctly assigned to the monthly, annual and lifetime products.
- All five metadata/localization/review-note/contact sets, base free pricing, 15 product localizations/prices, annual one-week eligible trials and US-only availability read back.
- Current age-rating answers, including the social-feature questions, read back; wellness is declared for NutriLoupe. Its consumer-wellness medical-device declaration is saved as No.
- All 15 public privacy/support/marketing URLs returned HTTP 200. Project/submission validators passed for eight metadata sets and 24 local product identifiers/localizations.

## Retained earlier evidence — separately qualified

The purchase implementation and local catalog were unchanged by the current storage/repair fixes. The five local StoreKit UI methods retained in [purchase results](Batch2PurchaseResults.md) are:

- `Batch2PurchaseFlowTests/test01ThreeLocalPlansAndLifetimeRelaunch()`

They cover monthly/annual/lifetime access, relaunch persistence and legal links using local StoreKit transactions, not real payments.

The earlier [nine-method eight-app/mode pipeline](Batch2TestResults.md) and [51-method main regression inventory](TestResults.md) retain their own dates, targets and candidate qualifications. The current repair rerun is linked above; the rest are not relabeled as new current-build executions. The cue-card renderer's six paper/card combinations and 28 visually reviewed PDF pages remain separately recorded in that pipeline evidence.

## Owner actions left last

The saved privacy answers need the owner's publication attestation. The final native automatic-synchronization checks need the Mac unlocked. After privacy publication, the app-version items can be attached to the five prepared review drafts; final App Review submission remains separate. [Preparation status](../Submission/Batch2Preparation.md).
