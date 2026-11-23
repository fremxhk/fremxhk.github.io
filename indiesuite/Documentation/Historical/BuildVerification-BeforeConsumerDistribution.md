# Build verification

Current Batch 1 candidates: VaultGlass build 4 archived from local Git commit `00bf075` (warranty reconciliation implemented in `747c8e2`); BioPulse Local build 6 and ClauseShield build 3 from `eec440b`. Version 1.0.0, built with Xcode 27.1 / Swift 6.4 / iOS SDK 27.1; minimum iOS/iPadOS 27.0. The updated Pro screen distinguishes verified lifetime/subscription access from purchase choices. Package construction is verified separately from runtime and service readiness.

| App | Build | Archive signature/resources | Production export | SHA-256 of IPA |
| --- | --- | --- | --- | --- |
| VaultGlass | 4 | Passed | Passed | `926aa39530f23dc1f60c4d3c098ce4ab01eb4adb79d18c46c1980c0276f3c4ea` |
| BioPulseLocal | 6 | Passed | Passed | `8a1f5510d5908ad79a15e59f6479828c240bd13ed11f1c0412e78dd87f05bbd0` |
| ClauseShield | 3 | Passed | Passed | `0e7f9ac70a838fa1277917d38d670638781ebeac5161b2c4c69e20b79b71d698` |

Checks passed: deep/strict code-signature validation; exact bundle IDs, version/build and minimum OS; matching CloudKit containers; required HealthKit/App Group entitlements; all privacy resources including the widget App Group reason; no private key files in app bundles; Debug screenshot/seeding/empty-fixture launch flags absent from Release executables. Exported packages disable debugging and use production push and iCloud entitlements.

The initial BioPulse upload was rejected for a missing HealthKit update purpose string. Both Health purpose strings are now present and checked before archiving. The app requests read-only HealthKit access.

App Store upload, processing, selected builds, purchase draft attachments and final owner-input gates are recorded in [submission status](../Submission/README.md). No physical-device QA, App Review approval or public release is implied.

## Physical QA distribution preparation

An earlier 2/3/2 archive set was exported with Apple's `release-testing` method for the registered iPhone. Deep/strict signatures pass, and executable UUIDs plus every Mach-O `__TEXT` section hash match their original archives. Only distribution signing changed; no app source was rebuilt. This allows hardware checks to proceed separately from pending TestFlight invitation acceptance. It does not certify TestFlight receipt behavior or live purchases.

The independent physical UI-test host has no dependency on the three app targets, supplies no QA entitlement arguments and has no StoreKit configuration. The completed 35-method physical baseline used TestFlight 2/5/2, including the BioPulse neutral-question regression. Current 4/6/3 candidates require their own completed physical results; those checks and native video work remain pending. See the version-qualified physical result report; earlier execution is not relabeled as a run of a newer binary.

## Five additional studios

Verified 18 November 2026. All five replacement archives and production exports passed validation, uploaded from their signed archives and processed to VALID. They are selected in unsubmitted App Store drafts with manual release. All five designated internal TestFlight groups have the selected build in `IN_BETA_TESTING`, with automatic new-build notifications disabled.

The candidates were archived sequentially on the Xcode SSD using Xcode 27.2 (27B52), Swift 6.4.2 and iOS SDK 27.2; deployment target remains iOS/iPadOS 27.0. All five archive source records identify clean commit `99c37a4`. This includes the durable CloudKit cache fix, source-grounded repair validation, readable repair labels and the fitted cue-card preview.

Archive/export checks covered exact identity/version/build, minimum OS, deep/strict signatures, privacy resources, matching app-specific CloudKit containers, absence of private keys and Debug QA launch flags, and a single intended app per archive without QA hosts. Production exports disallow debugging and carry production APNs/iCloud entitlements. EchoBrief and RecallGlass carry microphone/speech usage descriptions; Speech linkage is absent from the other three. Upload version-number management is disabled.

| Validated local export | Build | IPA SHA-256 |
| --- | --- | --- |
| DeductGlass | 2 | `3caad0ad08501d52cad9e6d2b5bbe057edfa2eccfb6a2581ef98b70f06509a34` |
| EchoBrief | 2 | `62370ecf99c4e6780c97db7fd1a2bbfe151f1f568df11e674fa63955fb4956bb` |
| NutriLoupe | 2 | `debefc1b4f18d8b7d03113a64bf11c2c7238c6d5f8ff0b276fb7904b803ee020` |
| TorqueShield | 2 | `b64e6d807828ae231db6f93b67b7091b59d4c795cd8baac767e6402e8accc712` |
| RecallGlass | 3 | `9e87c8293f2f2e9ccb33cc3573f04ba9876b15b01334b126ec48eeb07dd056d3` |

These hashes identify the validated local exports. Apple uploads are generated from the same versioned signed archives; App Store processing and selection are read back separately. Earlier build 1 packages and RecallGlass builds 1/2 are preserved privately and are not relabeled as the replacements.

Validation: `python3 Scripts/verify-archives.py DeductGlass EchoBrief NutriLoupe TorqueShield RecallGlass` and the same names with `Scripts/verify-exports.py`. [Current UI evidence](Batch2UIResults.md), [production schemas](CloudKitDeployment.md) and [service checks](ProductionServiceResults.md) remain separate from package verification. Signing material, IPAs and raw diagnostics are excluded from Git.

## Current candidates

The earlier TestFlight 2/5/2 baseline passed 35 distinct physical methods. Paid-state capture review exposed purchase offers still visible alongside active access. Source `eec440b` hides those offers, presents lifetime status or Apple subscription management, resolves access before presenting prices, and blocks an additional purchase while verified access is active.

Subsequent 3/6/3 testing exposed an incomplete VaultGlass warranty draft. Build 4 reconciles the generated response against saved source facts and supplies a complete evidence checklist. The current regression report contains 51 distinct passing methods, including three warranty core regressions and the fresh-receipt-to-letter UI check. Exact-candidate physical checks and final native Pro demonstrations remain pending. Current production IPAs were revalidated against the manifest, including exact build numbers, identities and SHA-256 fingerprints above, using `Scripts/verify-exports.py`. App Store processing and draft selection are recorded separately in the submission status.

## Submission checkpoint — 17 November 2026

These exact 4/6/3 candidates were submitted to App Review and verified as Waiting for Review. Privacy responses were published, content rights saved and each app version included with its three purchase products and subscription group. Release remains manual. No binary changed and no additional device tests were performed for this metadata submission. See [submission status](../Submission/README.md).
