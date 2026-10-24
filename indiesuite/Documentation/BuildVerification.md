# Build verification

Current Batch 1 candidate source: local Git commit `eec440b`. Version 1.0.0, built with Xcode 27.1 / Swift 6.4 / iOS SDK 27.1; minimum iOS/iPadOS 27.0. The updated Pro screen distinguishes verified lifetime/subscription access from purchase choices. Package construction is verified separately from runtime and service readiness.

| App | Build | Archive signature/resources | Production export | SHA-256 of IPA |
| --- | --- | --- | --- | --- |
| VaultGlass | 3 | Passed | Passed | `5b8c69853060ea27d1a44342b7d8f626423cc9ef5a3381e3cc2fa97c9cdeeec4` |
| BioPulseLocal | 6 | Passed | Passed | `8a1f5510d5908ad79a15e59f6479828c240bd13ed11f1c0412e78dd87f05bbd0` |
| ClauseShield | 3 | Passed | Passed | `0e7f9ac70a838fa1277917d38d670638781ebeac5161b2c4c69e20b79b71d698` |

Checks passed: deep/strict code-signature validation; exact bundle IDs, version/build and minimum OS; matching CloudKit containers; required HealthKit/App Group entitlements; all privacy resources including the widget App Group reason; no private key files in app bundles; Debug screenshot/seeding/empty-fixture launch flags absent from Release executables. Exported packages disable debugging and use production push and iCloud entitlements.

The initial BioPulse upload was rejected for a missing HealthKit update purpose string. Both Health purpose strings are now present and checked before archiving. The app requests read-only HealthKit access.

App Store upload, processing, selected builds, purchase draft attachments and final owner-input gates are recorded in [submission status](../Submission/README.md). No physical-device QA, App Review approval or public release is implied.

## Physical QA distribution preparation

An earlier 2/3/2 archive set was exported with Apple's `release-testing` method for the registered iPhone. Deep/strict signatures pass, and executable UUIDs plus every Mach-O `__TEXT` section hash match their original archives. Only distribution signing changed; no app source was rebuilt. This allows hardware checks to proceed separately from pending TestFlight invitation acceptance. It does not certify TestFlight receipt behavior or live purchases.

The independent physical UI-test host has no dependency on the three app targets, supplies no QA entitlement arguments and has no StoreKit configuration. The completed 35-method physical baseline used TestFlight 2/5/2, including the BioPulse neutral-question regression. Current 3/6/3 Pro-screen candidates are being installed and verified separately. See the version-qualified physical result report; earlier execution is not relabeled as a run of a newer binary.

## Five additional studios

RecallGlass, DeductGlass, EchoBrief, NutriLoupe and TorqueShield compiled successfully in Release for generic iOS hardware (Swift 6.4 complete concurrency, iOS SDK 27.1). These are unsigned compilation checks, not installed-device execution or App Store distribution exports. Debug `--qa-studio-pro`, `--qa-empty-fixture` and `--store-screenshots` launch flags were absent from each executable. The final RecallGlass anchor refinement was rebuilt separately and passed. Source implementation: `715acba`; archive configuration correction: `0fa625a`.

Distribution verification now requires App Store application metadata and exactly one app in each archive. A rejected BioPulse build 5 attempt included the independent QA host and was therefore a generic archive. The QA host is now `SKIP_INSTALL=YES`; the rejected artifact is retained privately and is not counted as an export pass. The corrected archive contains only BioPulseLocal.app and its production export passed signature/entitlement checks.

Apple processing rejected the first build 5 upload because unused shared speech code required a speech privacy declaration. Speech transcription now resides in `IndieCoreAudio`, linked only by EchoBrief, RecallGlass and their sequential test target. The corrected BioPulse Release archive has no Speech framework dependency or `SFSpeech` symbols; the archive verifier enforces both. The rejected artifact is retained privately and excluded from current evidence. Corrected source: `84ae61c`; upload processing remains separate from export verification.

The earlier corrected build 5 upload processed as VALID and was available to internal testers. It is superseded by the current build 6 candidate. Automatic tester notifications remain disabled.

## Current Pro-access candidates

The earlier TestFlight 2/5/2 baseline passed 35 distinct physical methods. Reviewing its paid-state captures exposed purchase offers still visible alongside active access. Source `eec440b` now hides those offers, presents lifetime status or Apple subscription management, resolves access before presenting prices, and blocks an additional purchase while verified access is active. Updated signed candidates are 3/6/3. Their production exports pass strict signatures, production capabilities, no unused speech references and no Debug-flag checks. The full 47-method regression passes, including all active-access UI checks. All three builds processed as VALID, are available to the existing internal tester group and are selected for unsubmitted version 1.0.0 drafts. Exact-candidate physical checks and native Pro demonstrations are being completed.
