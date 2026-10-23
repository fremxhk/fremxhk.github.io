# Build verification

Executable-source candidate: local Git commit `6982a49`. Version 1.0.0, built with Xcode 27.1 / Swift 6.4 / iOS SDK 27.1. Minimum iOS/iPadOS: 27.0. This verifies package construction; physical runtime and live Apple services remain release gates.

| App | Build | Archive signature/resources | Production export | SHA-256 of IPA |
| --- | --- | --- | --- | --- |
| VaultGlass | 2 | Passed | Passed | `8031fee84c62c4707a4f32f21e4c063580e6e4cf998e46c6f99f51cd3762ef65` |
| BioPulseLocal | 3 | Passed | Passed | `bf5acd9cbe6bb6b3ef9eff76e535fc1842338a7f8202f91ce60f853fc5a7c0e2` |
| ClauseShield | 2 | Passed | Passed | `0ddf9d550ecae59b4064aa2e80584286b74930bbbca184355043c52fce882205` |

Checks passed: deep/strict code-signature validation; exact bundle IDs, version/build and minimum OS; matching CloudKit containers; required HealthKit/App Group entitlements; all privacy resources including the widget App Group reason; no private key files in app bundles; Debug screenshot/seeding/empty-fixture launch flags absent from Release executables. Exported packages disable debugging and use production push and iCloud entitlements.

The initial BioPulse upload was rejected for a missing HealthKit update purpose string. Both Health purpose strings are now present and checked before archiving. The app requests read-only HealthKit access.

App Store upload, processing, selected builds, purchase draft attachments and final owner-input gates are recorded in [submission status](../Submission/README.md). No physical-device QA, App Review approval or public release is implied.

## Physical QA distribution preparation

All three archived candidates were exported with Apple's `release-testing` method for the registered iPhone. Deep/strict signatures pass, and executable UUIDs plus every Mach-O `__TEXT` section hash match their original archives. Only distribution signing changed; no app source was rebuilt. This allows hardware checks to proceed separately from pending TestFlight invitation acceptance. It does not certify TestFlight receipt behavior or live purchases.

The independent physical UI-test host has no dependency on the three app targets. It cannot replace them with Debug apps, supplies no QA launch arguments and has no StoreKit configuration. Runner construction passed; physical test execution is pending the device's UI-automation authentication prompt.
