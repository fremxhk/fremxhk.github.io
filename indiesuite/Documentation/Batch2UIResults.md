# Current five-app UI workflow results

Verified 18 November 2026 using Xcode 27.2. All five named XCTest workflows passed on native iPhone 17 and 13-inch iPad Pro profiles running iOS 27.0. The complete retest passed **10 executions of five distinct workflow methods**, with zero failures or skips in those two completed bundles. A later repair-label refinement passed its same workflow again on both profiles; those repeats do not increase the distinct-method count.

Fresh installs used normal durable storage and the real free allowance. The UI launch arguments were empty: no empty in-memory fixture, forced Pro entitlement or screenshot override was used. Installed build identities and executable hashes were recorded before execution. These are Debug simulator executions; distribution package checks are reported separately.

Only one task-owned simulator ran at a time, each app terminated before the next, two build jobs were allowed, and parallel tests/clones were disabled. XCTest teardown also terminates an app after a failed case.

| App | Method in `Batch2StudioFlowTests` | iPhone | iPad | Candidate build |
| --- | --- | --- | --- | --- |
| DeductGlass | `test01DeductReceiptVerificationAndBinder()` | Passed | Passed | 2 |
| EchoBrief | `test02EchoBriefCommitmentReviewAndExport()` | Passed | Passed | 2 |
| NutriLoupe | `test03NutriIngredientJournalAndAssociations()` | Passed | Passed | 2 |
| TorqueShield | `test04TorqueEstimateDecisionAndLeaseWorkspace()` | Passed | Passed | 2 |
| RecallGlass | `test05RecallStudyAndSpeechPrintStudio()` | Passed | Passed | 3 |

## Assertions exercised

- **DeductGlass:** sample receipt import, source evidence review, verification state, tax method workspace, readable CPA PDF and the separate Singapore recordkeeping path.
- **EchoBrief:** sample transcript, meeting costs and commitments, owner/task/date confirmation, intentionally simulated reminder dispatch, and readable meeting PDF. No real reminder or calendar event is created by the simulator path.
- **NutriLoupe:** ingredient analysis, journal save and 14-day association view.
- **TorqueShield:** source-grounded repair items, evidence detail, persisted decline decision and VIN/lease workspace. Final labels show readable triage and decision text.
- **RecallGlass:** deck creation, exact-source answer/semantic grade, review scheduling, speech cue generation, stage rehearsal, PDF export/preview and full-first-sheet fit on both profiles.

## Selected case provenance

- iPhone / DeductGlass 2: `TestResults/Batch2-Normal-Launch-20261118-213740/iPhone.xcresult`; source snapshot `ce53ccebe3c6596f259d242bf5429d710511f05e`.
- iPhone / EchoBrief 2: `TestResults/Batch2-Normal-Launch-20261118-213740/iPhone.xcresult`; source snapshot `ce53ccebe3c6596f259d242bf5429d710511f05e`.
- iPhone / NutriLoupe 2: `TestResults/Batch2-Normal-Launch-20261118-213740/iPhone.xcresult`; source snapshot `ce53ccebe3c6596f259d242bf5429d710511f05e`.
- iPhone / TorqueShield 2: `TestResults/Torque-Native-Labels-20261118-215751/iPhone.xcresult`; source snapshot `0e555aa7535ff0c99135689612e0ab28e7e2bdef`.
- iPhone / RecallGlass 3: `TestResults/Batch2-Normal-Launch-20261118-213740/iPhone.xcresult`; source snapshot `ce53ccebe3c6596f259d242bf5429d710511f05e`.
- iPad / DeductGlass 2: `TestResults/Batch2-Normal-Launch-20261118-213740/iPad.xcresult`; source snapshot `d0c53f4fa867cfbffb820ceaead08fbccedad099`.
- iPad / EchoBrief 2: `TestResults/Batch2-Normal-Launch-20261118-213740/iPad.xcresult`; source snapshot `d0c53f4fa867cfbffb820ceaead08fbccedad099`.
- iPad / NutriLoupe 2: `TestResults/Batch2-Normal-Launch-20261118-213740/iPad.xcresult`; source snapshot `d0c53f4fa867cfbffb820ceaead08fbccedad099`.
- iPad / TorqueShield 2: `TestResults/Torque-Native-Labels-20261118-215751/iPad.xcresult`; source snapshot `0e555aa7535ff0c99135689612e0ab28e7e2bdef`.
- iPad / RecallGlass 3: `TestResults/Batch2-Normal-Launch-20261118-213740/iPad.xcresult`; source snapshot `d0c53f4fa867cfbffb820ceaead08fbccedad099`.

The full clean retest is retained in `TestResults/Batch2-Normal-Launch-20261118-213740`; the final repair-label captures are in `TestResults/Torque-Native-Labels-20261118-215751`. Source snapshots can differ for documentation-only commits and the scoped repair-label update; installed candidate versions and individual Passed cases are checked separately.

## Native store images

The 32 selected PNGs are opaque RGB captures at 1206 × 2622 (16 phone images) and 2064 × 2752 (16 tablet images). Their original bytes are retained without resizing. All five contact sheets were visually reviewed, including repair details, associations, PDFs and the fitted cue-card sheet. [Capture inventory](Previews/AppStore/Batch2/README.md).

The initial normal-launch run retained four passing flows and one failed repair case. It exposed a model response that repeated itemized prices in the service name and changed brake safety triage. That case was not counted as a pass. Source reconciliation and two [repair regression methods](RepairGroundingResults.md) now cover that failure; the full clean UI retest passed afterward. Earlier design/capture attempts remain version-qualified historical evidence and are not relabeled as current candidate results.
