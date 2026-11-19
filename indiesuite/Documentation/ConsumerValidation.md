# Consumer revision validation

Updated 19 November 2026. This is an in-progress evidence inventory, not a release-readiness declaration. The new consumer candidates have not yet been submitted.

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

The export checks preserve multipage PDF content, a rotated page, a full-page receipt image and source text. Visual inspection then found that source PDF artwork could overlap a binder label. The clipping correction is in commit `90819d6`; the focused result above predates that final layout correction, which still needs its own rerendered verification.

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

The original three-app suite adds lab-source correction/evidence, contract wording editing, local search and explicit Pro dismissal checks. Full iPhone/iPad simulator, StoreKit, current offline storage, signed archives and current screenshots remain pending. All 24 product review notes and six editable app-version metadata sets were saved and read back; VaultGlass and ClauseShield’s app-version text is held until their earlier review submissions are replaced. RecallGlass’s description was corrected to its implemented text/PDF manuscript input.

## Publication and pricing

All 24 US product prices were written and read back as $0.99 monthly, $5.99 annual and $14.99 lifetime, per app. Availability remains USA-only. The public consumer guide, pricing and health-storage documents and two health privacy pages were committed and pushed in public commit `4b19877`; HTTP readback matched the committed bytes for pricing, health policy and both privacy pages.

Screenshot requirements were rechecked against Apple’s [current screenshot specifications](https://developer.apple.com/help/app-store-connect/reference/app-information/screenshot-specifications/) on 19 November 2026. The required current sets are Dynamic Island medium iPhone and 13-inch iPad; the selected native capture profiles use 1206 × 2622 and 2064 × 2752 pixels. Native captures must retain their dimensions and opaque pixels; image-delivery completion is checked separately from candidate identity and UI-flow results.
