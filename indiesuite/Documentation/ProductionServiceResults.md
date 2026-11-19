> **19 November 2026 consumer revision:** Fresh direct production service checks passed for all six cloud-enabled apps: VaultGlass (2 record types), ClauseShield (2), DeductGlass (2), EchoBrief (2), TorqueShield (3) and RecallGlass (4), totaling 15 types. Each created/read/queried/updated/deleted its own synthetic records and deleted its isolated test zone. Current source health policy keeps BioPulse Local and NutriLoupe on-device. The five-app report below records earlier implementation history, including NutriLoupe; it does not describe the new health-storage policy. The six app-specific automatic mirroring lifecycles also passed across five separate process phases per app, including independent initial/updated import and server deletion cleanup; see [consumer validation](ConsumerValidation.md).

# Production CloudKit service checks

The five app-specific production service preflights passed on 18 November 2026. A Mac Catalyst test client was signed for each app’s own bundle identifier, private container and **Production** CloudKit environment; signature and environment checks ran before execution. These are authenticated service checks, not execution of the iOS distribution IPA.

| App | Application record types checked | Create / direct read / indexed query / update / delete | Isolated test zone removed |
| --- | --- | --- | --- |
| DeductGlass | 2 | Passed | Verified |
| EchoBrief | 2 | Passed | Verified |
| NutriLoupe | 2 | Passed | Verified |
| TorqueShield | 3 | Passed | Verified |
| RecallGlass | 4 | Passed | Verified |

Each run created a uniquely named zone in the app’s private production database and one synthetic record per application record type. It saved and directly fetched the identifier, confirmed an exact identifier query against the deployed index, changed and read back the identifier with a new server change tag, deleted the record, and required a direct lookup to return `unknownItem`. The run then deleted its own isolated test zone. No user records or unrelated zones were changed.

There are **five app-qualified service runs spanning 13 application record types**. These are not 65 distinct XCTest methods. Each client’s executable hashes and individual service result are retained privately.

## Separate synchronization verification

The [production schemas](CloudKitDeployment.md) and [20 offline storage methods](CloudStorageResults.md) passed their respective checks. Automatic SwiftData export, independent-store import, later updates, receipt asset transfer and deletion propagation are checked by a separate native client. The first direct-launch attempts saved durable SQLite rows and connected to CloudKit, but did not confirm an export before the timeout; they are retained as unsuccessful attempts. A normal native launch is pending an unlocked Mac session. These attempts are not counted as synchronization passes.

Direct CloudKit service success does not, by itself, establish automatic SwiftData synchronization. The remaining native test uses the actual app models and container factory, a unique fixture identifier, independent durable stores and server deletion readback.

## Apple references

- [How Core Data synchronization is scheduled](https://developer.apple.com/documentation/technotes/tn3163-understanding-the-synchronization-of-nspersistentcloudkitcontainer)
- [Private CloudKit database access](https://developer.apple.com/documentation/cloudkit/ckcontainer/privateclouddatabase)
