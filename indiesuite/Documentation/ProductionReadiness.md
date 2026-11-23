# Consumer App Review submission

2026-11-24: **Submitted for App Review.** All eight revised candidates have been submitted for App Review, with automatic release after approval. Availability and paid products are USA-only.

| App | Version / build | Processing | Review preparation |
| --- | --- | --- | --- |
| VaultGlass | 1.0.0 / 5 | VALID, selected | WAITING_FOR_REVIEW; submitted |
| BioPulse Local | 1.0.0 / 7 | VALID, selected | WAITING_FOR_REVIEW; submitted |
| ClauseShield | 1.0.1 / 4 | VALID, selected | WAITING_FOR_REVIEW; submitted |
| DeductGlass | 1.0.0 / 3 | VALID, selected | WAITING_FOR_REVIEW; submitted |
| EchoBrief | 1.0.0 / 3 | VALID, selected | WAITING_FOR_REVIEW; submitted |
| NutriLoupe | 1.0.0 / 3 | VALID, selected | WAITING_FOR_REVIEW; submitted |
| TorqueShield | 1.0.0 / 3 | VALID, selected | WAITING_FOR_REVIEW; submitted |
| RecallGlass | 1.0.0 / 4 | VALID, selected | WAITING_FOR_REVIEW; submitted |

## Completed evidence

- All 121 distinct target-qualified methods passed, with zero failures/skips in current completed bundles. Native iPhone/iPad profiles and local purchase checks ran sequentially. [Every method](ConsumerTestInventory.md) · [Scope and retained diagnostics](ConsumerValidation.md).
- All six cloud-enabled apps passed five separate-process production SDK synchronization phases each, covering 15 record types and independent cleanup. Signed SDK-client checks are distinguished from iOS IPA execution. [Production lifecycle inventory](ProductionMirroringResults.md).
- Both health apps use protected on-device storage, without CloudKit synchronization. Migration, encrypted archives, atomic merges, backup limits and supported preference restoration were verified. [Storage policy](HealthStoragePolicy.md).
- All eight signed archives/production exports passed validators, processed to VALID and were selected. [Package fingerprints](BuildVerification.md).
- All 44 native storefront PNGs and 24 product-review PNGs were reviewed, delivered COMPLETE and matched Apple's source checksums/file sizes. Native dimensions and opaque pixels are preserved. Additional workflow/access captures remain linked in the gallery.
- All 24 US product prices were saved/read back: $0.99/month, $5.99/year and $14.99 lifetime per app. Eligible annual trials remain one week. Metadata, privacy publication, content rights, age information, review contacts, account-free sample instructions and required health declarations are saved. Existing approved purchase versions are retained; pending versions are attached with the current app versions.
- All eight current builds are assigned to existing designated-tester internal groups and are IN_BETA_TESTING. Public links and automatic notifications are disabled.

## Submission scope

Apple received the revised submissions. Automatic release after approval is enabled; see SubmissionStatus.md for the recorded review states.

The [consumer guide](ConsumerGuide.md) states supported inputs, corrections, recovery and explicit coverage limits. The [research](ConsumerReadinessResearch.md) explains the completed feature/pricing decisions. The suite does not claim comprehensive laboratory/legal coverage, clinical validation, vehicle history, market-price feeds or guaranteed extraction accuracy. Source review, corrections and portable records remain available. App Review approval and customer feedback are subsequent outcomes, not guarantees inferred from a test pass.
