# Five-studio UI test results

**Five distinct UI workflows passed; no failures or skips in the listed bundles.** All used the same iOS 27.0 iPhone 17e simulator sequentially.

Source: `715acba` (app behavior), with archive-only configuration follow-up `0fa625a`.

These tests use synthetic documents, isolated in-memory stores and a Debug-only QA entitlement. They verify interaction and rendering, not paid purchases, physical audio, EventKit dispatch or cloud services. The entitlement flag is excluded from Release builds. Repeated runs do not increase the method count.

| Method | Latest passing evidence |
| --- | --- |
| `Batch2StudioFlowTests/test01DeductReceiptVerificationAndBinder()` | `Studio-Final-Schema-And-Grounding.xcresult` |
| `Batch2StudioFlowTests/test02EchoBriefCommitmentReviewAndExport()` | `Studio-Final-Schema-And-Grounding.xcresult` |
| `Batch2StudioFlowTests/test03NutriIngredientJournalAndAssociations()` | `Studio-Final-Schema-And-Grounding.xcresult` |
| `Batch2StudioFlowTests/test04TorqueEstimateDecisionAndLeaseWorkspace()` | `Studio-Final-Schema-And-Grounding.xcresult` |
| `Batch2StudioFlowTests/test05RecallStudyAndSpeechPrintStudio()` | `RecallGlass-Final-UI.xcresult` |

Coverage: receipt verification, tax-year-scoped US CPA PDF and separate Singapore records PDF; meeting summary/source-linked commitment review, confirmed Simulator dispatch preview and PDF; ingredient details, symptom entry and 14-day chart; repair quote/item review, a saved decline decision and lease assumptions; study creation, typed exact-answer grading with a correct/Good suggestion, answer reveal and FSRS grade, speech creation, stage timer start/pause/reset and cutout preview.

Filled fields retain visible labels. Calendar dates inferred only from relative weekdays remain unset. Captures wait for navigation transitions to settle. The PDF and deterministic-math suites are reported separately in [eight-app results](Batch2TestResults.md).

| Completed bundle | Passed executions |
| --- | ---: |
| `Studio-Final-Schema-And-Grounding.xcresult` | 5 |
| `RecallGlass-Final-UI.xcresult` | 1 |

Earlier offscreen-control, accessibility-identifier, keyboard/confirmation-switch targeting and interrupted attempts are retained privately and excluded here. These results do not establish production readiness; see [open release gates](ProductionReadiness.md).

## Native store capture rerun — 17–18 November 2026

The same five methods each achieved a passing execution on iPhone 17 and 13-inch iPad simulators using Xcode 27.2. The first four apps use their build 1 captures on iOS 27.0. RecallGlass uses build 2 with the fitted PDF preview and strengthened full-sheet visibility assertion; selected destination runtimes are listed below. An additional full build 2 tablet control passed on iOS 27.2. These are ten passing executions of five existing methods, not ten new distinct tests. The profiles ran one at a time.

| App / method | iPhone latest Passed case | iPad latest Passed case |
| --- | --- | --- |
| DeductGlass: `test01DeductReceiptVerificationAndBinder()` | `TestResults/Batch2-Store-Captures-20261117-202817/iPhone.xcresult` | `TestResults/Batch2-Store-Captures-20261117-204958/iPad.xcresult` |
| EchoBrief: `test02EchoBriefCommitmentReviewAndExport()` | `TestResults/Batch2-Store-Captures-20261117-202817/iPhone.xcresult` | `TestResults/Batch2-Store-Captures-20261117-204958/iPad.xcresult` |
| NutriLoupe: `test03NutriIngredientJournalAndAssociations()` | `TestResults/Batch2-Store-Captures-20261117-202817/iPhone.xcresult` | `TestResults/Batch2-Store-Captures-20261117-204958/iPad.xcresult` |
| TorqueShield: `test04TorqueEstimateDecisionAndLeaseWorkspace()` | `TestResults/Batch2-Store-Captures-20261117-202817/iPhone.xcresult` | `TestResults/Batch2-Store-Captures-20261117-204958/iPad.xcresult` |
| RecallGlass: `test05RecallStudyAndSpeechPrintStudio()` | `TestResults/Recall-iPhone-Build2-20261118-022834/iPhone.xcresult` | `TestResults/Recall-iPad-Build2-20261118-093414/iPad.xcresult` |

The original iPhone capture bundle passed all five cases with zero failures/skips; the selected table retains its first four cases and uses the separate build 2 RecallGlass phone run. The tablet bundle `TestResults/Batch2-Store-Captures-20261117-204958/iPad.xcresult` contains four Passed cases and a canceled RecallGlass attempt. Only its four individually verified Passed cases contribute to the table. RecallGlass build 2 was rerun separately after the fitted-preview correction and test geometry guard; both selected focused phone/tablet bundles passed one case each with zero failures/skips. This is a case-level passing inventory, not a claim that every historical bundle is green.

The first tablet attempt exposed full-window drag coordinates landing outside centered form sheets. Scrolling was corrected to use visible form bounds. A subsequent rehearsal attempt measured fixed controls against the underlying page navigation bar; tablet rehearsal now uses its own visible navigation bar. The latter branch affects only RecallGlass rehearsal, so the four already passing tablet cases were preserved and the complete affected RecallGlass method was rerun. Failed and interrupted attempts remain private and are excluded from the latest passing case selection. All interaction, grading, timer, verification and export assertions remain intact; the full-sheet preview-fit assertion was added for build 2. Pre-migration storage failures, stalled-wait runner failures, and the SSD runner termination before connection remain retained and excluded from passing counts. Host load was elevated; its causal role was not established. The earlier build 1 iOS 27.0 tablet run failed on invalid accessibility transition geometry. The first build 2 minimum-runtime tablet run failed during an accessibility snapshot query. Those attempts remain excluded; the selected build 2 results and runtimes below identify the actual completed retests.

The selected [native store captures](Previews/AppStore/Batch2) contain synthetic content and exclude QA home screens and the simulator-only dispatch diagnostic. [Local purchase evidence](Batch2PurchaseResults.md) is separate. No physical device was used.

RecallGlass build 2 selected tablet runtime: iOS 27.0. Complete method assertions include study creation, typed grading, answer reveal, FSRS, speech creation, stage timer start/pause/reset and first-sheet PDF fit. Candidate build and source provenance were read from the generated app and saved alongside each passing result.

RecallGlass build 2 phone and iOS 27.2 tablet control used source `5432a63`. The selected iOS 27.0 tablet run and signed archive used `4dab198`, which adds the archive-action configuration guard without changing app behavior. The iOS 27.2 control is retained at `TestResults/Recall-iPad-Build2-20261118-025205/iPad.xcresult`; it is additional evidence, not a second selected screenshot set.
