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

The focused RecallGlass harness compiled with the rehearsal-bar correction. An early retry failed to reset the dedicated simulator because of insufficient disk space. After free space recovered, reset, boot and RecallGlass installation succeeded. The latest focused prebuilt run, `TestResults/Recall-iPad-Clean-20261117-224731/iPad.xcresult`, failed while preparing the XCTest runner at `XCTWaiter(StallHandling) handleStalledWait:`. It contains zero passes and one runner error; no app method began, so no app assertion outcome is inferred. Observed host load averages were approximately 775–896; load is a possible contributor, not an established cause. The simulator was shut down and no additional test was launched. Completion requires a healthy-host rerun of the complete method, then visual review and upload of its five native tablet captures. Existing passing evidence is unchanged.

## SSD retry — 18 November 2026

The [workspace migration](Workspace.md) preserved source, signed archives and raw test evidence using full SHA-256, symlink, permission and Git checks. The complete RecallGlass tablet method was attempted again from `/Volumes/XCode/Developer/IndieSuite` on the same dedicated iPad profile, without parallel testing. The first attempt timed out reapplying appearance after boot. The subsequent attempt reused the already configured simulator and unchanged installed app; functional assertions were not removed or skipped.

`TestResults/Recall-iPad-SSD-20261117-234744/iPad.xcresult` ended on 18 November with zero passes and one runner error: “Test crashed with signal kill before establishing connection.” No app method began, so this is not an app assertion result. The host load average returned to approximately 730; five other projects' Xcode builds and five other simulators were active during a resource check. Resource pressure is a possible contributor, not a demonstrated root cause. Further attempts await those other jobs being paused. This task's simulator was shut down, its QA lock released, and no physical device was used. Existing passing results and the 27 delivered native screenshots are unchanged; RecallGlass's five tablet screenshots remain pending.
