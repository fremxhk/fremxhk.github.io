# Consumer release readiness

Updated 19 November 2026. The revised eight-app suite is **in validation**, with manual release and USA-only availability. Revised candidates have not been submitted. Compilation, earlier uploads and historical test results do not establish readiness of these revisions.

## Candidate scope

| App | Revised build | Storage |
| --- | --- | --- |
| VaultGlass | 5 | Private CloudKit with durable local cache |
| BioPulse Local | 7 | On-device protected health storage |
| ClauseShield | 4 | Private CloudKit with durable local cache |
| DeductGlass | 3 | Private CloudKit with durable local cache |
| EchoBrief | 3 | Private CloudKit with durable local cache |
| NutriLoupe | 3 | On-device protected health storage |
| TorqueShield | 3 | Private CloudKit with durable local cache |
| RecallGlass | 4 | Private CloudKit with durable local cache |

The [consumer research and acceptance criteria](ConsumerReadinessResearch.md) explain the implemented search, full recovery, correction and draft-protection changes. The [consumer guide](ConsumerGuide.md) describes supported workflows and limits. US prices are $0.99 monthly, $5.99 annual and $14.99 lifetime per app; all 24 saved prices were read back. Eligible annual purchases retain a one-week trial. Prices displayed in the app come from StoreKit.

## Evidence already completed

- Production schemas and direct service lifecycle checks cover all 15 record types across the six cloud-enabled apps. All six also passed five separate-process SDK synchronization phases: create/export, independent import, update, independent updated import and deletion/cleanup. These are signed Mac Catalyst clients using actual model sources, not execution of the iOS distribution IPAs. See [the full inventory](ProductionMirroringResults.md).
- Complete portable archives cover all eight apps. The five new formats preserve 13 model types and 122 scalar fields, attachments and child relationships. Focused tests cover atomic merging, duplicate/dangling references, incompatible formats, preference whitelists, encryption and the 100 MB boundary.
- PDF regression checks and independent rendered-page review caught and corrected missing source-page heading/footer glyphs. Original source PDF pages remain selectable vector content, including page rotation.
- Focused StoreKit checks passed signed-period boundaries and lifetime refunds for all eight namespaces. Real accelerated monthly terms also expired correctly with the default system clock. Cached access now enforces the verified expiration without waiting for an SDK refresh.
- All eight app records passed the required metadata-field audit; all 24 product review notes were saved and read back. Privacy declarations are published. Health-app storage/protection declarations were separately verified.

The owner has authorized **automatic release after Apple approval** for all eight verified replacement versions. Apply this choice after current candidates pass validation and are selected; current superseded storefront settings are not the release authorization for the replacements.

## Remaining release gates

The [current validation ledger](ConsumerValidation.md) distinguishes completed focused tests from full regression gates. A failed or unfinished attempt is never counted as a pass, repeated runs do not increase the number of distinct methods, and skips do not count as tested.

1. Complete current sequential native iPhone/iPad workflows, dark/largest-text checks, paid UI, core, evaluations and app-host storage regressions with source hashes recorded.
2. Visually review and export current native storefront screenshots and all product review images; preserve native dimensions and opaque pixels.
3. Produce, sign and verify all eight revised archives and distribution exports, then obtain valid processed App Store builds.
4. Select current builds, verify current metadata, screenshot delivery, TestFlight assignments and unsubmitted review drafts. Replace earlier review candidates only after their replacements are verified.
5. Publish the final method inventory, screenshots and readiness evidence to GitHub and verify the remote commit and public files.
6. Resolve the existing Mac/Vision storefront availability scope before the final readiness decision; current automated consumer UI evidence targets iPhone/iPad.

The suite does not claim clinical validation, comprehensive legal coverage, a vehicle history service, universal laboratory-marker support or guaranteed error-free extraction. Consumers can inspect sources, correct supported facts and export their records. AI interpretation, symptom associations and comparisons have explicit limits. A finite validation program cannot guarantee that no customer will ever report a problem.
