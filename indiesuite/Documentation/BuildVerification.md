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

RecallGlass, DeductGlass, EchoBrief, NutriLoupe and TorqueShield compiled successfully in Release for generic iOS hardware (Swift 6.4 complete concurrency, iOS SDK 27.1). These are unsigned compilation checks, not installed-device execution or App Store distribution exports. Debug `--qa-studio-pro`, `--qa-empty-fixture` and `--store-screenshots` launch flags were absent from each executable. The final RecallGlass anchor refinement was rebuilt separately and passed. Original implementation: `715acba`; archive configuration correction: `0fa625a`. On 24 October 2026 all five were rebuilt serially after the `IndieCoreAudio` isolation and shared access changes. Every Release compilation passed. The actual outputs passed bundle/build/minimum-OS, privacy-manifest and all four Debug-launch-flag exclusion checks. EchoBrief and RecallGlass contain the required microphone/speech purpose strings; the other three have no Speech framework or `SFSpeech` references. This used generic iOS build destinations and did not access a physical device.

Distribution verification now requires App Store application metadata and exactly one app in each archive. A rejected BioPulse build 5 attempt included the independent QA host and was therefore a generic archive. The QA host is now `SKIP_INSTALL=YES`; the rejected artifact is retained privately and is not counted as an export pass. The corrected archive contains only BioPulseLocal.app and its production export passed signature/entitlement checks.

Apple processing rejected the first build 5 upload because unused shared speech code required a speech privacy declaration. Speech transcription now resides in `IndieCoreAudio`, linked only by EchoBrief, RecallGlass and their sequential test target. The corrected BioPulse Release archive has no Speech framework dependency or `SFSpeech` symbols; the archive verifier enforces both. The rejected artifact is retained privately and excluded from current evidence. Corrected source: `84ae61c`; upload processing remains separate from export verification.

The earlier corrected build 5 upload processed as VALID and was available to internal testers. It is superseded by the current build 6 candidate. Automatic tester notifications remain disabled.

## Current candidates

The earlier TestFlight 2/5/2 baseline passed 35 distinct physical methods. Paid-state capture review exposed purchase offers still visible alongside active access. Source `eec440b` hides those offers, presents lifetime status or Apple subscription management, resolves access before presenting prices, and blocks an additional purchase while verified access is active.

Subsequent 3/6/3 testing exposed an incomplete VaultGlass warranty draft. Build 4 reconciles the generated response against saved source facts and supplies a complete evidence checklist. The current regression report contains 51 distinct passing methods, including three warranty core regressions and the fresh-receipt-to-letter UI check. Exact-candidate physical checks and final native Pro demonstrations remain pending. Current production IPAs were revalidated against the manifest, including exact build numbers, identities and SHA-256 fingerprints above, using `Scripts/verify-exports.py`. App Store processing and draft selection are recorded separately in the submission status.
