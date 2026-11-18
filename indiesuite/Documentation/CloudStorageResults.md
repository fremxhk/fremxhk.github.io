# Cloud storage readiness results

Offline checks completed on 18 November 2026 using Xcode 27.2 and one signed-out iPhone 17e simulator running iOS 27.0. Five app-specific hosts ran sequentially with two build jobs and parallel testing disabled. **20 target-qualified methods passed, with zero failures or skips in these selected bundles.** There are four shared method bodies, exercised independently in each app host.

| App | Model constraints / cloud-store load | SQLite reopen / relationships / receipt | Signed-out durable cache | Legacy-store adoption |
| --- | --- | --- | --- | --- |
| DeductGlass | Passed | Passed | Passed | Passed |
| EchoBrief | Passed | Passed | Passed | Passed |
| NutriLoupe | Passed | Passed | Passed | Passed |
| TorqueShield | Passed | Passed | Passed | Passed |
| RecallGlass | Passed | Passed | Passed | Passed |

## Exact methods

Each app target is named `<App>CloudReadinessTests`. The four methods are:

- `CloudReadinessTests/test01CloudKitModelConstraintsAndManifest()`
- `CloudReadinessTests/test02SQLiteDurabilityRelationshipsAttachmentsAndCascade()`
- `CloudReadinessTests/test03SignedOutFallbackUsesDurableLocalStore()`
- `CloudReadinessTests/test04LegacyLocalStoreAdoptsCloudCacheWithoutLosingRecords()`

Model checks use the actual SwiftData types, generate the managed-object model, check optional/inverse relationships and attribute compatibility, and load a CloudKit-configured persistent store. Disk tests save and reopen an isolated SQLite store, verify values and relationships, preserve a 512 KiB external receipt payload, and verify cascade deletions. The signed-out check invokes the actual container factory without its in-memory option. Legacy adoption checks that adding the CloudKit cache configuration preserves existing records at the same URL.

These are source-level development tests. Distribution-package signatures and runtime/service evidence are reported separately. The account-dependent Apple schema dry-run and initialization methods are excluded from this offline selection and executed through the authenticated Mac preparation tool instead. They are not counted as simulator passes.

The first attempt combined model checks with Apple’s authenticated schema dry run, which failed because no iCloud account was signed in. The initial host also linked a duplicate model library. Those attempts are retained and excluded. The corrected hosts resolve the shared module from their app, and offline model/store validation is separated from authenticated schema operations. No app assertion was removed to turn an authenticated operation into an offline pass.

Selected result root: `TestResults/Batch2-CloudReadiness-20261118-200731`.

Storage source SHA-256 at reporting: `0c42b201e2e83256b4d65f09b80e80493839f5689e579970d99b4ce6513a5d6c`.
