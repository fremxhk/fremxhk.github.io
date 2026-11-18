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

Verified 18 November 2026. DeductGlass, EchoBrief, NutriLoupe and TorqueShield retain version 1.0.0 build 1 from source `4f7b15e`. RecallGlass uses version 1.0.0 build 2 from source `4dab198`, correcting the fitted first-sheet PDF preview. The archive-scheme guard prevents QA hosts and test bundles from entering app archive actions. All five packages are preserved and were revalidated on the Xcode SSD; they were built sequentially with Xcode 27.2 (27B52), Swift 6.4.2 and iOS SDK 27.2; deployment target remains iOS/iPadOS 27.0. They processed to VALID and are selected in unsubmitted, manual-release App Store drafts.

Archive and export validators checked exact identity/version/build, deep/strict signatures, privacy resources, app-specific CloudKit containers and absence of Debug QA launch flags or private key files. Exported packages disable debugging and carry production APNs/iCloud entitlements. EchoBrief and RecallGlass include microphone/speech usage strings; Speech linkage is absent from the other three. Each archive contains only its intended app, with no QA host. These package checks do not establish deployed production cloud schemas or live service behavior. Earlier RecallGlass build 1 artifacts are preserved privately and are not relabeled as build 2.

| Export | Build | IPA SHA-256 |
| --- | --- | --- |
| DeductGlass | 1 | `d155c7365867010ec28e6b58695bd902ef1c869e21997e2e90e93697b09f29fe` |
| EchoBrief | 1 | `0a6bfd48413b176a82f1ff156789b4911040c65a0eb8763be24ba84c35950ccc` |
| NutriLoupe | 1 | `fab23170b341d55402c06a8011f8ae4ae759d8ceb5c5f0c5a691d6b433a23546` |
| TorqueShield | 1 | `7ce7e442137747a7ee262973ba0d93151386e7458c1208358cd617ee38c7589a` |
| RecallGlass | 2 | `c327f64912ee47384ee731e10dc32619aea529d131848e507e0922fa339d80bb` |

Validation: `python3 Scripts/verify-archives.py DeductGlass EchoBrief NutriLoupe TorqueShield RecallGlass` and the same names with `Scripts/verify-exports.py`. Signing material, IPAs and raw diagnostics remain excluded from Git. See [five-app submission preparation](../Submission/Batch2Preparation.md) for draft status and remaining decisions.

## Current candidates

The earlier TestFlight 2/5/2 baseline passed 35 distinct physical methods. Paid-state capture review exposed purchase offers still visible alongside active access. Source `eec440b` hides those offers, presents lifetime status or Apple subscription management, resolves access before presenting prices, and blocks an additional purchase while verified access is active.

Subsequent 3/6/3 testing exposed an incomplete VaultGlass warranty draft. Build 4 reconciles the generated response against saved source facts and supplies a complete evidence checklist. The current regression report contains 51 distinct passing methods, including three warranty core regressions and the fresh-receipt-to-letter UI check. Exact-candidate physical checks and final native Pro demonstrations remain pending. Current production IPAs were revalidated against the manifest, including exact build numbers, identities and SHA-256 fingerprints above, using `Scripts/verify-exports.py`. App Store processing and draft selection are recorded separately in the submission status.

## Submission checkpoint — 17 November 2026

These exact 4/6/3 candidates were submitted to App Review and verified as Waiting for Review. Privacy responses were published, content rights saved and each app version included with its three purchase products and subscription group. Release remains manual. No binary changed and no additional device tests were performed for this metadata submission. See [submission status](../Submission/README.md).
