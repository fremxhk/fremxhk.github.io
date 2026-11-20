# Consumer revision validation

Updated 20 November 2026. This is an in-progress evidence inventory, not a release-readiness declaration. The new consumer candidates have not yet been submitted.

## Current preparation checkpoint

Visual review of the completed `Consumer-Native-UI-20261120-092027` phone/tablet cohorts exposed mid-word wrapping in shared PDF reports. All 13 methods had passed on each profile, but the screenshots showed ordinary words broken across lines. The original three-app cohort was interrupted before making a production-source correction; no partial cohort is accepted.

The existing evidence-export method now checks intact prose words and preservation of a long unbroken reference. `Consumer-Word-Wrap-20261120-101753` reproduced the defect: “We” became separate “W” and “e” tokens. After correcting the renderer to break at whitespace and split only overlong references, `Consumer-Word-Wrap-20261120-101918` passed both PDF methods with zero failures/skips. All six exported PDF pages were rendered with Poppler and manually reviewed, including the rotated source page and full-page receipt image.

A subsequent evaluation attempt, `Consumer-Evaluations-Isolated-20261120-102609`, returned VaultGlass's live three-product catalog rather than the configured local test catalog. Both catalog methods now require their exact local product sets before attempting transactions. The evaluation scheme explicitly matches its VaultGlass test host, and workspace StoreKit file references use the documented `../` prefix; project verification checks both. Clean command-line probes still required native Xcode initialization of the local fixture. After selecting the local configuration and running the app through Xcode, the simulator contained all 24 expected local product IDs, and `Consumer-Evaluations-Isolated-20261120-110222` passed both focused catalog/verified-lifetime methods with zero failures/skips. The complete 33-method evaluation cohort remains required; application monetization logic was unchanged.

The shared production renderer changed, so complete validation and screenshots must run again against the corrected source. The earlier [84-method checkpoint](ConsumerCheckpointTests.md) and the preceding 26 native workflow executions remain historical evidence for their actual inputs; they are not current release passes. Revised candidates remain unsubmitted, with no revised signed packages uploaded yet.

The owner unlocked the Mac and paused other heavy jobs before the successful pre-correction native cohorts. Current tests remain sequential, with two build jobs and one task-owned simulator active at a time. Earlier simulator system crashes remain documented below; improved host conditions do not establish a definitive root cause.

App Store version readback still shows VaultGlass 1.0.0 awaiting review, BioPulse Local 1.0.0 developer-rejected, ClauseShield's separate 1.0.1 update draft prepared, and the five newer 1.0.0 drafts prepared. Current versions still have manual release while replacements are validated. The owner has authorized submission and automatic release after approval once all checks are complete; that policy will be applied to the verified replacements before submission. ClauseShield's older 1.0.0/build 3 is live and is separate from this revision.

## Focused source checks

Result: **21 passed, 0 failed, 0 skipped**, serialized on the same iPhone 17e simulator. Result bundle: `TestResults/Consumer-Focused-20261119-093349/Focused.xcresult`. Thirteen consumer workflow checks, two evidence-export checks, two migration checks and four health-storage/backup/container checks passed.

| Test method | Result |
| --- | --- |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/allFiveBackupsPreserveEveryScalarAttachmentAndRelationship()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/mergeKeepsEditedExistingRecordsAndRejectsBrokenArchivesAtomically()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/searchUsesEveryWordAndHandlesAccentsWhitespaceAndEmptyQueries()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/csvPreservesQuotedUnicodeAndBlocksFormulaCells()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/labCorrectionValidatesUnitsUpdatesDerivedValuesAndClearsStaleSummary()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/repeatedMealsDoNotReuseSymptomsAndCorrectionsRecomputeIngredients()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/expenseCSVReimportsQuotedHeadersCRLFAndRejectsUnsupportedCurrencyWithoutPartialSave()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/manualStudyCardsPreserveOrResetHistoryOnlyWhenChosen()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/editedContractWordingFeedsAcceptedDraftWithoutChangingEvidence()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/repairCorrectionsValidateNumbersAndKeepDecisionAndSource()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/meetingEditsKeepTranscriptCommitmentsAndCostAssumptions()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/savedExpenseCalendarDatesDoNotChangeWhenDeviceTimeZoneChanges()` | Passed |
| `SequentialWorkspaceQASuite/ConsumerReadinessTests/anOversizedBackupCannotBeExportedAsAnUnimportableFile()` | Passed |
| `SequentialWorkspaceQASuite/EvidenceExportTests/binderIncludesEverySourcePDFPageAndRotation()` | Passed |
| `SequentialWorkspaceQASuite/EvidenceExportTests/binderPreservesSourceTextAndProvidesFullPageImageEvidence()` | Passed |
| `SequentialWorkspaceQASuite/ExpenseMigrationTests/earlierSQLiteStoreKeepsEveryReceiptAndAmountWhenDateFieldIsAdded()` | Passed |
| `SequentialWorkspaceQASuite/ExpenseMigrationTests/earlierArchiveWithoutCalendarDateStillImports()` | Passed |
| `SequentialWorkspaceQASuite/HealthStorageAndBackupTests/healthCachesReopenWithoutCloudKitAndRequestBackupExclusion()` | Passed |
| `SequentialWorkspaceQASuite/HealthStorageAndBackupTests/studioPreferencesRestoreOnlyWhenSelectedAndNeverGrantPurchases()` | Passed |
| `SequentialWorkspaceQASuite/HealthStorageAndBackupTests/clinicianPrepPreferencesUseAValidatedWhitelist()` | Passed |
| `SequentialWorkspaceQASuite/HealthStorageAndBackupTests/concurrentWindowsShareOnePersistentContainer()` | Passed |

The export checks preserve multipage PDF content, a rotated page, a full-page receipt image and source text. Independent Poppler rendering exposed missing label glyphs after source-page embedding. Static report fonts in `cde8667` corrected the heading and footer in the rerendered rotated-page output. Both focused PDF methods passed in `Consumer-PDF-Probe-20261119-122147`, and the full 31-method core rerun passed in `Consumer-Core-20261119-122338`, with no failures or skips. Application and test source hashes stayed unchanged during that run.

An earlier broader run, `Consumer-20261119-Full/Core.xcresult`, passed 27 methods with no failures or skips. Its 17 consumer/evidence/migration methods overlap this focused run; repeated passes are not additional distinct methods. Its ten pipeline checks predate the latest health-storage/shared-container correction and require a current regression run.

## Production services and schema

Fresh direct production service checks passed for VaultGlass, ClauseShield, DeductGlass, EchoBrief, TorqueShield and RecallGlass, covering all 15 record types: create, read, indexed query, changed record tag, update, deletion and isolated test-zone cleanup. The fixtures are synthetic and scoped to each test run. These are direct CloudKit API checks, not proof of automatic SwiftData mirroring.

VaultGlass and ClauseShield’s schemas, and DeductGlass’s additional source-text/calendar-date fields, were deployed through the CloudKit Console and verified by its Changes Deployed confirmation. BioPulse Local and NutriLoupe use on-device health storage and are excluded from the automatic-cloud release scope.

The one-process synchronization harness stopped on its retired-container-release assertion. The replacement uses five distinct app processes: creation/export, independent initial import, reopened-writer update, independent updated import, and reopened-writer deletion with direct server cleanup verification.

All six cloud-enabled apps have now passed all five phases: VaultGlass, ClauseShield, DeductGlass, EchoBrief, TorqueShield and RecallGlass. That is 30 separate process phases covering 15 record types; see the [full lifecycle inventory](ProductionMirroringResults.md). The two receipt apps also verified a 1,200,000-byte attachment and its SHA-256 after independent import. Each completed client exited before the next app was started. These are signed Mac Catalyst SDK-client checks using the actual model sources and app-specific production containers; they are distinct from execution of the iOS distribution IPAs.

## Native UI and release checks

The expanded five-app suite contains 13 UI methods, including a three-viewport contrast/description audit for each app. The initial Release attempt passed receipt/binder/Singapore, meeting/commitment/PDF, nutrition/journal/pattern and repair/lease flows, then was stopped for diagnosis. It was not a completed passing suite: historical synthetic use had exhausted RecallGlass’s persistent free allowance; the native exporter used Copy instead of the test’s assumed Cancel; a list tap stopped scrolling without opening the food record; and the system discard popover omitted its cancel-role button. The failure bundles are retained.

The revised tests complete the native export, verify navigation before editing and keep scroll gestures above the keyboard. Draft discard and record deletion use explicit native alerts. Product UI reserves space for subscription loading and provides a 44-point Close Pro control. Search focuses the library; saved records precede secondary tools. Tax and vehicle settings initialize before StoreKit requests and pin the active workspace. Editing verified receipt facts now clears their verification and stale memo, with a UI regression added to the receipt flow.

Only the two task-owned capture profiles were reset for fresh-install allowance tests, after an inventory guard verified that their non-system apps belonged to this workspace. No entitlement override is used in the Release five-app flow. Purchase and quota checks remain independent. The full updated suites and captures still need passing results.

The original three-app suite adds lab-source correction/evidence, contract wording editing, local search and explicit Pro dismissal checks. Full iPhone/iPad simulator, StoreKit, current offline storage, signed archives and current screenshots remain pending. All eight app records passed the required metadata-field audit. USA-only app availability and manual release were completed and read back for the original three, matching the existing five-app territory setup. All 24 product review notes and six editable app-version metadata sets were saved and read back; VaultGlass and ClauseShield’s app-version text is held until their earlier review submissions are replaced. RecallGlass’s description was corrected to its implemented text/PDF manuscript input.

## Publication and pricing

All 24 US product prices were written and read back as $0.99 monthly, $5.99 annual and $14.99 lifetime, per app. Availability remains USA-only. The public consumer guide, pricing and health-storage documents and two health privacy pages were committed and pushed in public commit `4b19877`; HTTP readback matched the committed bytes for pricing, health policy and both privacy pages.

Screenshot requirements were rechecked against Apple’s [current screenshot specifications](https://developer.apple.com/help/app-store-connect/reference/app-information/screenshot-specifications/) on 19 November 2026. The required current sets are Dynamic Island medium iPhone and 13-inch iPad; the selected native capture profiles use 1206 × 2622 and 2064 × 2752 pixels. Native captures must retain their dimensions and opaque pixels; image-delivery completion is checked separately from candidate identity and UI-flow results.

## Evaluation environment isolation

The combined evaluation run retained a StoreKit inconsistency: the artificial test session reported an expired subscription while StoreKit 2 still returned its earlier signed future expiration and subscribed status. Those failed attempts are retained and are not reported as passes. Transaction-delivery cleanup is asserted before artificial expiry. The final test orchestration runs each StoreKit method in a separate app-host process, sequentially on the same simulator, and runs the remaining document/regression methods separately. The release policy now checks cached subscription access against the verified signed expiration on every access, without waiting for a refresh. Focused signed-boundary/refund checks passed all eight app namespaces in `Consumer-Expiry-Probe-20261119-131107`; real 30-second monthly terms passed all eight with the default system clock in `Consumer-Real-Term-20261119-131510`. The final 33-method evaluation gate remains open until its full current run passes. Artificial-expiry diagnostics are retained as failures, not counted as release passes.

## Full workflow corrections

`Consumer-Native-UI-20261119-132146` completed its first iPhone suite with 9 passes and 4 failures, and did not advance to iPad. It is retained as a failed release-gate attempt. The receipt test searched downward for a field above the viewport; the nutrition check inspected feedback outside its viewport. Its observation fixture and feedback scrolling were made explicit without relaxing product validation. The amount-only accessibility label was given its receipt/deduction context.

The fourth failure reproduced a product defect: SwiftUI's optimistic row deletion left the row hidden after cancellation, even after waiting ten seconds. A shared non-destructive swipe request now opens the existing destructive confirmation, so the row is removed only after approval. The same correction covers the affected libraries, study cards and nutrition entries. `Consumer-Delete-Probe-20261119-133554` retained the failure; the corrected flow passed `Consumer-Delete-Probe-20261119-133726` with no failures or skips, including cancellation and confirmed deletion. A complete current native-profile rerun remains required.


The next full iPhone attempt, `Consumer-Native-UI-20261119-133942`, passed 11 methods, including receipt correction, nutrition journaling and cancellation/confirmed deletion, and retained two failures. A source recording showed that the CSV row was beneath the floating search field: scrolling now respects that overlay, and navigation is verified before checking the export. The CSV flow passed its focused follow-up.

The contrast audit successively identified secondary body text, native section headings and a primary button. The five new apps now use the existing adaptive readable secondary/action colors, explicit readable section headers and opposing foregrounds on prominent buttons. `Consumer-Contrast-CSV-Probe-20261119-140114/Delete.xcresult` passed the full five-app, three-viewport light-appearance audit with zero failures/skips and unchanged source hashes. An earlier diagnostic reused a retained Singapore profile while a fresh-install setup method expected US; that failed setup remains diagnostic evidence, not a release pass. The normal full run resets only verified task-owned fixtures.

The same current five-app audit also passed dark appearance at the largest accessibility text size in `Consumer-Dark-LargeText-Probe-20261119-140414/NewFive.xcresult`, with zero failures/skips and unchanged source hashes. This focused evidence does not replace the required complete iPhone/iPad regression runs.


`Consumer-Native-UI-20261119-140753` was intentionally interrupted after a saved-food row lookup failed; completed cases are not relabeled as a full pass. The row existed briefly under the navigation bar, and the old edge test scrolled it farther away. Scrolling now uses the row center to reverse direction, shorter 250-point/second drags with an end hold, and a bounded opposite-direction search for absent lazy rows. The complete nutrition workflow passed focused iPhone (`Consumer-Nutrition-Scroll-Probe-20261119-141615`) and iPad (`Consumer-Nutrition-iPad-Probe-20261119-141810`) checks, each with zero failures/skips and unchanged source hashes. A fresh complete run remains required.


Further repeated UI diagnostics separated interaction failures from product results. A patterns link could be intercepted by the floating root search area. Live navigation-bar indices could disappear while a composer closed, and right-edge drags could interact with controls/scroll indicators. The harness now derives navigation/keyboard/scroll-column geometry from an immutable hierarchy snapshot, keeps root-library taps above the floating search area, and uses slow gutter drags. Library navigation verifies the destination and retries only if the original root remains visible. Rehearsal controls use whole-window visibility because they precede the scrolling cue content.

On iPhone, `Consumer-Navigation-Repeat-Probe-20261119-151457` passed both nutrition and both complete RecallGlass executions, with zero failures/skips. The methods cover journal saving and patterns navigation; exact-answer grading; rehearsal timing/reset; returning to the fitted PDF preview; and availability of its export control. Repetitions are reliability checks, not additional distinct methods. Earlier intermittent diagnostic failures remain retained. The corresponding iPad run, `Consumer-Navigation-iPad-Repeat-Probe-20261119-152341`, also passed both methods twice with zero failures/skips and unchanged source hashes. The complete cohort runs remain pending.


The full iPhone Release suite in `Consumer-Native-UI-20261119-153311/iPhone.xcresult` passed all 13 methods with zero failures/skips. Native screenshot review then found a malformed TorqueShield advisor sentence: its declined-item list had no closing parenthesis and was empty before a decision. The prompt now asks a general deferral question until an item is declined, then names the declined items with complete punctuation. The in-progress iPad cohort was intentionally stopped for this correction. The entire current sequential validation is rerun; the earlier phone pass is historical evidence, not substituted for the corrected cohort.


The next full attempt, `Consumer-Native-UI-20261119-160458`, was interrupted after a lazy receipt-row lookup changed between separate existence and frame queries. The harness now reads target attributes from one immutable element snapshot; absent lazy rows remain scrollable without recording an XCTest lookup failure. `Consumer-Atomic-Receipt-Probe-20261119-161251/Delete.xcresult` passed the complete receipt correction/reverification method. `Consumer-Navigation-Repeat-Probe-20261119-161854/Delete.xcresult` passed nutrition and RecallGlass twice each, with zero failures or skips. These are focused checks, not a substitute for the final complete cohort. The native document picker's fixed Copy action is recognized by its own hittability instead of being scrolled as content; the complete recovery/export method remains in the full gate.


`Consumer-Native-UI-20261119-162943/iPhone.xcresult` passed all 13 Release methods with zero failures/skips. Its 16 main-flow captures were manually reviewed, with raw native checks of the corrected TorqueShield advisor prompt and EchoBrief commitment screen. The iPad passed its first five methods before the cohort was intentionally interrupted for an audio-cleanup correction. These results remain associated with their actual pre-correction source.

Runtime-warning inspection identified synchronous `AVAudioSession.setActive(false)` calls on ordinary screen cleanup, even when no recording had begun. The recorder now releases only a session it owns and uses Apple's [asynchronous activation](https://developer.apple.com/documentation/avfaudio/avaudiosession/activate(options:completionhandler:)) and [deactivation](https://developer.apple.com/documentation/avfaudio/avaudiosession/deactivate(options:completionhandler:)) APIs. Ordered transitions prevent a queued release from racing a subsequent start; closing the view invalidates pending permission/activation work before it can create a recording. The iPhone Release SDK build passed. Focused runtime-warning checks and a fresh full cohort remain required.

The pre-correction results also contain a frame-dimension diagnostic attributed to the RecallGlass app entry point at line zero, without an identified app-owned frame calculation in the affected native Form. The settled phone screens were inspected at native resolution and their card-editing/grading interactions passed. This diagnostic is retained rather than described as a zero-warning run; the final tablet layout review remains separate.


`Consumer-Audio-Cleanup-Probe-20261119-165552/Audio.xcresult` passed all three affected meeting/study/manual-card methods with zero failures/skips and **zero blocking audio-session runtime warnings**. Source hashes remained unchanged during the probe. The two retained frame-layout diagnostics are separate from the resolved audio warning. Background transitions now call the idempotent stop operation even while a start is pending, invalidating that request before recording can begin. Complete final-source native and regression cohorts follow this focused evidence.


On source `f8611df`, `Consumer-Native-UI-20261119-170242/iPhone.xcresult` passed all 13 Release methods with zero failures/skips and no blocking audio-session warnings. The iPad completed 12 passes and one failure: the commitment confirmation still read off immediately after a direct nested-switch tap. The capture showed the switch on screen and the synthesized-event coordinates matched its control. The failed suite is retained and is not counted as a release pass. The test now uses the existing visibility helper and waits up to five seconds for the named confirmation to become on before exercising dispatch/export; repeated iPad checks are required. No app source was changed for this interaction correction.

Evidence matching now checks every production/package/configuration file, shared test-host file and the result target's own test-method files. A change confined to a different known test-method target does not invalidate an unrelated completed suite. Production, shared-host and relevant test changes still invalidate evidence, including added/removed relevant files. Count assertions, zero failures/skips and the blocking-audio-warning check remain mandatory. This permits resuming completed independent phases without relabeling old or failed results.


`Consumer-Switch-Repeat-Probe-20261119-173646/Switch.xcresult` passed the complete meeting/commitment/dispatch-preview/PDF method three times on iPad (78.585, 55.530 and 49.223 seconds), with zero failures/skips and unchanged source hashes. The repetition is one distinct method. Actual-source provenance checks reject the preceding phone UI bundle after this relevant test edit, and accept the new matching focused bundle. The complete 13-method phone/tablet cohort is rerun before moving to the remaining independent suites.
