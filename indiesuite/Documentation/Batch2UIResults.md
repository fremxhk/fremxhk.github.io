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

## Native store capture progress — 17 November 2026

Xcode 27.2 / iOS 27.0: all five workflows passed on iPhone 17 in `TestResults/Batch2-Store-Captures-20261117-202817/iPhone.xcresult`. DeductGlass, EchoBrief, NutriLoupe and TorqueShield each have a Passed case in `TestResults/Batch2-Store-Captures-20261117-204958/iPad.xcresult`. That tablet bundle also contains a canceled RecallGlass case; the bundle as a whole is not green. RecallGlass is being rerun with a tablet-rehearsal-only navigation-bar correction. None of its canceled tablet executions is counted as passing.

Centered-sheet drag coordinates were corrected after the initial tablet attempt. The later rehearsal attempt measured visible fixed controls against the underlying page navigation bar; the focused retest uses the rehearsal bar instead. All functional assertions remain intact. Native captures are selected only from individually verified Passed cases. No physical device was accessed.

The focused RecallGlass harness compiled with the rehearsal-bar correction. Its next launch stalled before tests began; the subsequent clean-simulator retry could not erase the dedicated capture profile because of `NSPOSIXErrorDomain` code 28 (insufficient disk space). No pass is claimed for either attempt. Completion awaits actual free disk space. The existing passing phone and four passing tablet cases are preserved.
