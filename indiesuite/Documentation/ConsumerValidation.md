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

The one-process synchronization harness stopped on its retired-container-release assertion. A separate-process phase harness is being prepared so creation, independent import, reopened-writer update, independent updated import and deletion use distinct process lifecycles. No automatic-sync pass is claimed from an unfinished or failed attempt.

## Native UI and release checks

The expanded five-app suite contains 12 UI methods. Its first Debug attempt was interrupted after a lazy list row remained below the initial viewport; the fixture had saved, but the test waited before scrolling. The navigation helper now reveals lazy rows before waiting. The fresh Release suite is running, with no entitlement override and normal launch arguments. Its receipt/binder/Singapore and meeting/commitment/PDF flows have passed so far; this is not a completed 12-method suite result.

The original three-app suite adds lab-source correction/evidence, contract wording editing and local search checks. Full phone/tablet, StoreKit, current offline storage, signed archives and current screenshots remain pending. All 24 product review notes and the six editable app-version metadata sets were saved and read back; VaultGlass and ClauseShield’s app-version text is held until their earlier review submissions are replaced. Failed attempts and earlier build evidence are retained separately.

## Publication and pricing

All 24 US product prices were written and read back as $0.99 monthly, $5.99 annual and $14.99 lifetime, per app. Availability remains USA-only. The public consumer guide, pricing and health-storage documents and two health privacy pages were committed and pushed in public commit `4b19877`; HTTP readback matched the committed bytes for pricing, health policy and both privacy pages.
