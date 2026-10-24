# Recorded test results

Only completed result bundles are included. Repeated runs and parameter cases are identified separately; a simulator pass is not physical-device certification.

**51 distinct target-qualified test methods passed.** Repeated executions below do not increase that count. StoreKit expiry parameters for eight product namespaces are cases within one method.

Functional tests ran sequentially on iPhone 17e, iOS 27.0, with parallel testing and simulator cloning disabled. Accessibility scope and retained tooling exceptions are detailed in [Validation.md](Validation.md). Native StoreKit simulations are not live sandbox certification.


## Unique passing test inventory

| Target / test method | Result | Latest listed evidence |
| --- | --- | --- |
| `BioPulsePurchaseUITests/SequentialAppSmokeTests/test08PaywallPurchaseAndActiveAccessForTargetApp` | Passed | `BioPulsePurchaseUI.xcresult` |
| `BioPulsePurchaseUITests/SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro` | Passed | `BioPulsePurchaseUI.xcresult` |
| `ClausePurchaseUITests/SequentialAppSmokeTests/test08PaywallPurchaseAndActiveAccessForTargetApp` | Passed | `ClausePurchaseUI.xcresult` |
| `ClausePurchaseUITests/SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro` | Passed | `ClausePurchaseUI.xcresult` |
| `IndieSuiteEvaluationsTests/EntitlementConcurrencyTests/testMultipleWindowsShareFiveReservationsAndFailedWorkReleasesSlot` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/AppIntentsVerificationTests/structuredIntentResultsWithSeededLocalModels()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/authenticatedArchiveRoundTripAndWrongPassword()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/cloudCompatibleSchemaAndFullArchiveRecords()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/depreciationAndWarrantyDates()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/exactSuppliedPhenoAgeEquationAndMissingValues()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/historyDoesNotUseFutureReadings()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/receiptFactsOverrideUnsupportedModelValues()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/scannedImageOnlyPDFUsesOCR()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/syntheticDocumentsThroughLivePipeline()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/unitNormalization()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/weightedRiskAndOmissionsAndDiff()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/allRequiredMarkersRejectMissingNonfiniteAndNegativeValues()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/canonicalUnitAliasesAndEquivalentMeasurements()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/defensiveRiskBoundsAndProtectiveClauses()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/diffReconstructsBothVersionsWithRepeatedParagraphs()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/encryptedArchiveKeyMatchesPlatformPBKDF2()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/encryptedArchivesAuthenticateHeadersAndCiphertext()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/invalidVisionInputFailsCleanly()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/labAndContractArchivesPreserveAttachmentsAndDecisions()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/malformedAndIncompleteDocumentsDoNotInventFacts()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/multipagePDFRetainsFinalRecord()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/physicianPreparationAlwaysHasFiveDistinctQuestions()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/receiptTotalsExcludeSubtotalAndDatesAreValidated()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/textAccentPaletteMaintainsContrastOnCardsAndBadges()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/warrantyDraftNeverInventsAnUnrecordedSerial()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/warrantyDraftRepairsIncompleteHardwareModelResponse()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/warrantyDraftRetainsCompleteDocumentedBodyAndRepairsChecklist()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/StoreKitVerificationTests/fifteenBatch2ProductsAndVerifiedLifetimeEntitlements()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/StoreKitVerificationTests/nineProductsAndVerifiedLifetimeEntitlements()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/StoreKitVerificationTests/pendingDeclinedAndFailedPurchasesDoNotUnlock()` | Passed | `Evaluations.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/StoreKitVerificationTests/subscriptionExpiryAndLifetimeRefundRevokeAccess(bundle:)` | Passed | `Evaluations.xcresult` |
| `IndieSuiteUITests/AppIntentsVerificationTests/test01VaultIntentsAgainstLiveApp` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/AppIntentsVerificationTests/test02BioIntentAgainstLiveApp` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/AppIntentsVerificationTests/test03ClauseIntentAgainstLiveApp` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test01VaultGlassSeedAndLiveReceipt` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test02BioPulseSeedAndLiveLab` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test03ClauseShieldSeedAndLiveAudit` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test04CaptureLabStudioAndPrep` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test05CaptureContractReviewCards` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test06CaptureReceiptCoverageAndLedger` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test07BackupPoliciesAndBackgroundResumeAcrossApps` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test08PaywallPurchaseAndActiveAccessForTargetApp` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test09EmptyInstallFlowsNeedNoAccountOrExternalFiles` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test10MainScreenAccessibilityAudit` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro` | Passed | `UI.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test12WarrantyDraftRetainsReceiptFactsAndEvidence` | Passed | `Warranty4-Screen-20261024-135950.xcresult` |

## Result bundles and repeat executions

## Evaluations.xcresult

Result: **Passed**. 32 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `EntitlementConcurrencyTests/testMultipleWindowsShareFiveReservationsAndFailedWorkReleasesSlot()` | Passed |
| `IndieSuiteEvaluations/AppIntentsVerificationTests/structuredIntentResultsWithSeededLocalModels()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/syntheticDocumentsThroughLivePipeline()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/scannedImageOnlyPDFUsesOCR()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/receiptFactsOverrideUnsupportedModelValues()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/unitNormalization()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/depreciationAndWarrantyDates()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/exactSuppliedPhenoAgeEquationAndMissingValues()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/historyDoesNotUseFutureReadings()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/weightedRiskAndOmissionsAndDiff()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/authenticatedArchiveRoundTripAndWrongPassword()` | Passed |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/cloudCompatibleSchemaAndFullArchiveRecords()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/warrantyDraftRepairsIncompleteHardwareModelResponse()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/warrantyDraftRetainsCompleteDocumentedBodyAndRepairsChecklist()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/warrantyDraftNeverInventsAnUnrecordedSerial()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/physicianPreparationAlwaysHasFiveDistinctQuestions()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/textAccentPaletteMaintainsContrastOnCardsAndBadges()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/receiptTotalsExcludeSubtotalAndDatesAreValidated()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/malformedAndIncompleteDocumentsDoNotInventFacts()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/allRequiredMarkersRejectMissingNonfiniteAndNegativeValues()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/canonicalUnitAliasesAndEquivalentMeasurements()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/defensiveRiskBoundsAndProtectiveClauses()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/diffReconstructsBothVersionsWithRepeatedParagraphs()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/encryptedArchiveKeyMatchesPlatformPBKDF2()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/encryptedArchivesAuthenticateHeadersAndCiphertext()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/labAndContractArchivesPreserveAttachmentsAndDecisions()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/multipagePDFRetainsFinalRecord()` | Passed |
| `IndieSuiteEvaluations/ProductionRegressionTests/invalidVisionInputFailsCleanly()` | Passed |
| `IndieSuiteEvaluations/StoreKitVerificationTests/nineProductsAndVerifiedLifetimeEntitlements()` | Passed |
| `IndieSuiteEvaluations/StoreKitVerificationTests/fifteenBatch2ProductsAndVerifiedLifetimeEntitlements()` | Passed |
| `IndieSuiteEvaluations/StoreKitVerificationTests/subscriptionExpiryAndLifetimeRefundRevokeAccess(bundle:)` | Passed |
| `IndieSuiteEvaluations/StoreKitVerificationTests/pendingDeclinedAndFailedPurchasesDoNotUnlock()` | Passed |

Local evidence: `TestResults/20261024-131203/Evaluations.xcresult`.

## UI.xcresult

Result: **Passed**. 14 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `AppIntentsVerificationTests/test01VaultIntentsAgainstLiveApp()` | Passed |
| `AppIntentsVerificationTests/test02BioIntentAgainstLiveApp()` | Passed |
| `AppIntentsVerificationTests/test03ClauseIntentAgainstLiveApp()` | Passed |
| `SequentialAppSmokeTests/test01VaultGlassSeedAndLiveReceipt()` | Passed |
| `SequentialAppSmokeTests/test02BioPulseSeedAndLiveLab()` | Passed |
| `SequentialAppSmokeTests/test03ClauseShieldSeedAndLiveAudit()` | Passed |
| `SequentialAppSmokeTests/test04CaptureLabStudioAndPrep()` | Passed |
| `SequentialAppSmokeTests/test05CaptureContractReviewCards()` | Passed |
| `SequentialAppSmokeTests/test06CaptureReceiptCoverageAndLedger()` | Passed |
| `SequentialAppSmokeTests/test07BackupPoliciesAndBackgroundResumeAcrossApps()` | Passed |
| `SequentialAppSmokeTests/test08PaywallPurchaseAndActiveAccessForTargetApp()` | Passed |
| `SequentialAppSmokeTests/test09EmptyInstallFlowsNeedNoAccountOrExternalFiles()` | Passed |
| `SequentialAppSmokeTests/test10MainScreenAccessibilityAudit()` | Passed |
| `SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro()` | Passed |

Local evidence: `TestResults/Warranty4-UI-StoreKit-20261024-132433/UI.xcresult`.

## BioPulsePurchaseUI.xcresult

Result: **Passed**. 2 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test08PaywallPurchaseAndActiveAccessForTargetApp()` | Passed |
| `SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro()` | Passed |

Local evidence: `TestResults/Warranty4-UI-StoreKit-20261024-132433/BioPulsePurchaseUI.xcresult`.

## ClausePurchaseUI.xcresult

Result: **Passed**. 2 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test08PaywallPurchaseAndActiveAccessForTargetApp()` | Passed |
| `SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro()` | Passed |

Local evidence: `TestResults/Warranty4-UI-StoreKit-20261024-132433/ClausePurchaseUI.xcresult`.

## Warranty4-Screen-20261024-135950.xcresult

Result: **Passed**. 1 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test12WarrantyDraftRetainsReceiptFactsAndEvidence()` | Passed |

Local evidence: `TestResults/Warranty4-Screen-20261024-135950.xcresult`.
