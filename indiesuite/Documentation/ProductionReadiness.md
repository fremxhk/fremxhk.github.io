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
| Monetization | Nine product identities/types; annual one-week trial metadata; lifetime entitlement verification; monthly/annual expiry, cancellation of renewal and lifetime refund across all three product namespaces; concurrent five-slot quota reservations and cancellation release |

Normal UI checks cover receipt analysis/detail, lab analysis/panel, contract analysis/acceptance/pushback, charts/health comparison/doctor prep, insurance ledger/coverage, privacy/archive controls, background/resume, landscape, paywall purchase/restore and account-free empty-install entry. See the result report for completed scopes and counts, and [the accessibility audit scope](Validation.md#accessibility-audit-scope-and-tooling-exceptions) for its explicit native-control and viewport exceptions.

All three signed Release archives and production distribution exports passed signature, entitlement, identity and privacy-resource checks. Physical runtime, CloudKit production schema and live StoreKit service checks remain open.

App Store upload validation initially rejected BioPulse for a missing HealthKit update purpose string despite read-only authorization. The declaration is now present in the project manifest and generated Info.plist and is checked by the preflight script. A rejected upload is not counted as validation success.

## Material fixes found through testing

See [Validation.md](Validation.md) for the background crash, extraction grounding, entitlement ordering, encrypted-header authentication and risk-bound fixes. Earlier failures remain in local ignored result bundles for diagnosis.

## Required before calling these apps production ready

- Physical iPhone and iPad QA of the exact signed Release/TestFlight build, including cold launch, relaunch/data retention, camera imports, denied permissions, large PDFs and memory, widgets, alerts and accessibility.
- Model-ready and fallback behavior on hardware; supported language/region/device behavior and clear unsupported states.
- Development-to-production CloudKit schema validation and two-device synchronization, including signed-out fallback and explicit local/cloud transfer behavior.
- App Store sandbox/TestFlight product loading, paid monthly/annual/lifetime access, trial eligibility, renewal, cancellation, pending/failed purchases, refunds and restore. Local StoreKit simulation does not certify Apple's live service.
- Qualified review of medical/educational content and legal playbooks. No claim of clinical validation, regulated medical-device clearance or jurisdiction-wide legal accuracy is made.
- Final privacy/legal declarations, distribution territories, applicable trader/account details and completion of the unsubmitted review package. Current-size screenshots and IAP review images are prepared; final build selection and IAP draft associations are recorded in the submission status.
- Apple's requested physical-device launch-to-flow recording, real device/OS/build/video details in review notes, and truthful Guideline 2.1 reply.

The connected iPhone 18 Pro Max runs iOS 27.2 beta (24B115). Physical XCTest is awaiting the owner-completed system passcode prompt to enable UI automation. The direct device recording API is unsupported on this phone; native Control Center recording is being prepared. No physical app-flow test or recording has been completed yet. Public stable-OS and physical iPad coverage remain open. No app has been submitted for review or released by this preparation.
