# Production readiness review

Status: **release blocked pending the checks listed below**. Simulator tests are evidence for specific behavior; they do not establish physical-device, clinical, legal or App Store production readiness.

## Automated test coverage

[Every recorded test method and its result](TestResults.md) is listed separately. Tests run serially on the same iPhone 17e simulator. No failed/unfinished attempt is counted as a pass, no skipped check is counted as tested, and repeat runs do not increase the distinct-method total.

| Area | Passing coverage in the expanded core suite |
| --- | --- |
| Document extraction | Synthetic receipts, labs and contracts through the actual extraction/model-or-fallback pipeline; scanned image-only PDF OCR; malformed/empty/unsupported input failure |
| Receipt accuracy | Source total/date/serial/window precedence over unsupported model output; subtotal/tax and date-format regressions; no invented missing dates/identifiers; policy defaults remain estimates requiring verification; depreciation and warranty date calculations |
| Lab calculations | Exact independently calculated supplied equation; all required markers; missing, negative, NaN/infinite inputs; ages 1–130; 100 equivalent glucose measurements; Unicode unit aliases and canonical conversions; no future-history substitution |
| Contract review | Weighted score/omissions; duplicate and unsupported quotation rejection; protective wording; negated protections; hostile integer bounds and 10,000-clause score cap; paragraph diff reconstruction including repeated and empty paragraphs |
| Archives | Plain/encrypted round trips; independent Apple CommonCrypto PBKDF2 interoperability passed; wrong password; wrong app; authenticated header/ciphertext tampering; malformed salt/JSON; preservation of attachments, IDs, readings, previous versions, priorities and accepted/dismissed decisions |
| Exports | Multipage PDF with 100 records retains final record; all draft tones include accepted terms and exclude dismissed terms |
| Persistence/intents | Cloud-compatible SwiftData schema construction and full records; typed intent results; live intent UI checks recorded separately |
| Monetization | Twenty-four local product identities/types; annual one-week trial metadata; lifetime entitlement verification; monthly/annual expiry, cancellation of renewal and lifetime refund across all eight product namespaces; concurrent five-slot quota reservations and cancellation release |

Normal UI checks cover receipt analysis/detail, lab analysis/panel, contract analysis/acceptance/pushback, charts/health comparison/doctor prep, insurance ledger/coverage, privacy/archive controls, background/resume, landscape, paywall purchase/active-access persistence and account-free empty-install entry. See the result report for completed scopes and counts, and [the accessibility audit scope](Validation.md#accessibility-audit-scope-and-tooling-exceptions) for its explicit native-control and viewport exceptions.

All three signed Release archives and production distribution exports passed signature, entitlement, identity and privacy-resource checks. The remaining physical-device coverage, CloudKit production schema and live StoreKit service checks remain open.

App Store upload validation initially rejected BioPulse for a missing HealthKit update purpose string despite read-only authorization. The declaration is now present in the project manifest and generated Info.plist and is checked by the preflight script. A rejected upload is not counted as validation success.

## Material fixes found through testing

See [Validation.md](Validation.md) for the background crash, extraction grounding, entitlement ordering, encrypted-header authentication and risk-bound fixes. Earlier failures remain in local ignored result bundles for diagnosis.

## Required before calling these apps production ready

- Physical iPhone and iPad QA of the exact signed Release/TestFlight build, including cold launch, relaunch/data retention, camera imports, denied permissions, large PDFs and memory, widgets, alerts and accessibility.
- Model-ready and fallback behavior on hardware; supported language/region/device behavior and clear unsupported states.
- Development-to-production CloudKit schema validation and two-device synchronization, including signed-out fallback and explicit local/cloud transfer behavior. Apple documents a Debug-only Core Data schema initializer for SwiftData models, followed by verification and deployment in CloudKit Console: [SwiftData synchronization setup](https://developer.apple.com/documentation/swiftdata/syncing-model-data-across-a-persons-devices). Container registration alone is insufficient evidence of production-schema deployment.
- Verify current TestFlight product loading, owner-activated Pro access, relaunch persistence and paid-feature use. Monthly/annual lifecycle, trial metadata, pending/failed transactions and revocation are covered separately in the local StoreKit suite; those simulations are reported as local tests.
- Qualified review of medical/educational content and legal playbooks. No claim of clinical validation, regulated medical-device clearance or jurisdiction-wide legal accuracy is made.
- Final privacy/legal declarations, distribution territories, applicable trader/account details and completion of the unsubmitted review package. Current-size screenshots and IAP review images are prepared; final build selection and IAP draft associations are recorded in the submission status.
- Apple's requested physical-device launch-to-flow recording, real device/OS/build/video details in review notes, and truthful Guideline 2.1 reply.

The physical baseline used iPhone 18 Pro Max on iOS 27.2 beta (24B115), with UI automation enabled. The version-qualified baseline contains 35 distinct physical methods: 25 hardware data-processing tests and ten installed-app UI flows on TestFlight 2/5/2. Hardware review first caught too few clinician questions, then unsupported abnormality premises; BioPulse build 5 passed the corrected neutral-question flow. Subsequent paid-state screenshot review found purchase offers displayed to active lifetime users. Candidates 3/6/3 corrected that behavior. A subsequent VaultGlass warranty draft failure led to build 4; current 4/6/3 candidates require their own completed physical results. Native Control Center recording was verified in that baseline; each final clip must be imported and visually checked before publication. Public stable-OS and physical iPad coverage remain open. No app has been submitted for review or released by this preparation.

## Batch 2 status

The five new apps and 24-product local catalog are implemented. The eight-scheme pipeline/PDF run passed nine app/mode cases; the interactive studio suite passed five workflows. Subsequent screenshot review caught an exact-answer grading defect, now guarded by exact-answer matching and source-concept validation; its targeted unit/UI rerun passed. Explicit optional inverse relationships were added and the nine-case pipeline suite passed again. See [pipeline results](Batch2TestResults.md) and [UI results](Batch2UIResults.md). These scopes do not certify production readiness. The first runs exposed an icon sizing error, an ungrounded model quotation and unsafe SwiftData store-erasure teardown; each was corrected before the recorded passing reruns. New app provisioning, production cloud schemas, physical audio/EventKit behavior, actual-size printer checks, live purchases and qualified content review are separate gates. See [design and research decisions](Batch2DesignAndResearch.md).

## Current candidate checkpoint

The completed 35-method physical baseline used TestFlight 2/5/2. A later 3/6/3 bundle passed nine flows and failed the warranty draft check; it is excluded from the passing baseline. VaultGlass build 4 corrects source-fact completeness and the evidence checklist. Current 4/6/3 packages pass signed archive and production export verification. The full simulator regression contains 51 passing methods, including three warranty core regressions and the fresh-receipt-to-letter UI check. Final exact-build physical coverage and native Pro recordings remain pending; earlier passes are retained under their actual versions. No app has been submitted or released.
