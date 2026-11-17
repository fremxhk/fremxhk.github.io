# App Store submission status

**All three apps were submitted to App Review on 17 November 2026 and verified as Waiting for Review.** Release is manual after approval; no public release was performed.

| App | Version | Build | Submission time (Hong Kong) | Verified review state |
| --- | --- | --- | --- | --- |
| VaultGlass | 1.0.0 | 4 | 17 Nov 2026, 19:15:28 | Waiting for Review |
| BioPulse Local | 1.0.0 | 6 | 17 Nov 2026, 19:15:38 | Waiting for Review |
| ClauseShield | 1.0.0 | 3 | 17 Nov 2026, 19:15:49 | Waiting for Review |

## Submitted package

- Each app version is included with its monthly subscription, annual subscription, lifetime purchase and subscription-group version: nine purchase products and three groups in total.
- Data Not Collected privacy responses were published for all three after explicit confirmation of Apple’s publication agreement. Content rights are saved as Does Not Use Third-Party Content.
- Six-point review notes, account-free sample instructions, private review contacts, selected builds and manual release settings were saved and verified. Notes accurately disclose that no additional physical testing or current-build physical recording is available.
- Eleven native-size App Store screenshots and nine IAP review images were prepared and delivered. The required slots use actual 1206 × 2622 iPhone and 2064 × 2752 iPad captures.
- The existing [51-method simulator inventory](../Documentation/TestResults.md), [nine-case eight-app pipeline report](../Documentation/Batch2TestResults.md), [version-qualified physical baseline](../Documentation/PhysicalTestResults.md) and [signed package fingerprints](../Documentation/BuildVerification.md) remain unchanged. Metadata submission did not create new test passes.

## Configuration retained

Base apps are free. Each app offers monthly $4.99 USD, annual $29.99 USD with a one-week eligible USA introductory trial, and lifetime $79.99 USD products. Paid-product availability remains USA only. Converted prices in other pricing territories do not establish availability there. Automatic tester notifications remain disabled.

No developer-operated login or backend is required. Each app can generate its synthetic sample locally. Optional synchronization uses the user’s private iCloud container. Production CloudKit schema/two-device behavior and the other validation limits remain documented in [ProductionReadiness.md](../Documentation/ProductionReadiness.md); submission is not a certification of those unverified behaviors.

## Evidence scope

No physical device was accessed for this submission. Historical phone results remain associated with their actual older builds. The reviewer notes do not substitute simulator captures for a requested physical recording. Any subsequent App Review request must be answered with the evidence actually available.

Apple’s earlier metadata blockers—unpublished privacy answers and missing content rights—were resolved. Server submission acceptance and Waiting for Review were verified for all three apps. App Review approval and public availability remain separate outcomes.

See the [submission checklist](PreparationChecklist.md) and each app’s saved review notes for the submitted information.
