# Current consumer build verification

2026-11-24. All eight revised production archives and IPAs passed identity, deep/strict signature, version/build, minimum OS, privacy-manifest and entitlement checks. All eight uploaded builds processed to VALID and are selected and submitted for App Review.

| App | Build | Archive and production export | Local IPA SHA-256 |
| --- | --- | --- | --- |
| VaultGlass | 5 | Passed | `3f65aba010126c50e40fea7c4b41f51b7bd2bd5dbe302800bef1a76d8cd0d895` |
| BioPulse Local | 7 | Passed | `99a69fe4ea3bf062172875e2cc111fd4bbe011f3013118135f49778f7e8cadbe` |
| ClauseShield | 4 | Passed | `5dfc013782e739796e2eb5a2a951418aa7dcff53b973dee102415a4b203d2eeb` |
| DeductGlass | 3 | Passed | `76ac9bd9a179ef2ca41617fa2d239f016a98969c0da6f8952376d46085a32bb0` |
| EchoBrief | 3 | Passed | `4c7bdef94c537935e6a0ede14d31626bf330c09ea4073e93dcef0f6b7da58761` |
| NutriLoupe | 3 | Passed | `d9ac1aeaa9975908ec9cfccf4b5fd99359a191714cf65802f9ceed10f086234c` |
| TorqueShield | 3 | Passed | `d1745783dbe8a1654319f6c603293e6afd6f412d3650f386ffa42df481566502` |
| RecallGlass | 4 | Passed | `eb727603813547a4d14ca0fc40f9b6c0f53569145a900c4ce6b11b2c3ae45437` |

All archives were produced sequentially from clean source commit `7ec3b9c2db46c56b75b7d3ecd1a97ca6bf5d3fd2`, with two build jobs, on the Xcode SSD. Application, configuration, shared-host and relevant test-target hashes match the frozen inputs behind the [current 121-method inventory](ConsumerTestInventory.md). Documentation-only commits after archiving do not change these package fingerprints.

Checks include exact bundle identifiers; production CloudKit/APNs capabilities for six apps; no cloud/remote-notification entitlement and complete data protection for both health apps; HealthKit purpose strings; VaultGlass widget build/App Group/privacy consistency; audio purpose descriptions for the two audio-enabled apps; no unused Speech linkage in the other apps; no private key material or Debug QA launch flags in the Release executables; and debugging disabled in production exports. Validators: `Scripts/verify-archives.py` and `Scripts/verify-exports.py`, invoked for all eight app names.

Apple processing and selection, 68 matching native image deliveries and designated internal TestFlight assignments were read back independently. Package validity is separate from App Review approval. Earlier fingerprints remain [historical](Historical/BuildVerification-BeforeConsumerDistribution.md).
