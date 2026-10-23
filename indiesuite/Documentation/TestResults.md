# Recorded test results

Only completed result bundles are included. Repeated runs and parameter cases are identified separately; a simulator pass is not physical-device certification.

**45 distinct target-qualified test methods passed.** Repeated executions below do not increase that count. StoreKit expiry parameters for three apps are cases within one method.

Functional tests ran sequentially on iPhone 17e, iOS 27.0, `CEAF94B4-5BB2-46B3-A7B5-B075AB0098BC`, with parallel testing and simulator cloning disabled. Accessibility scope and retained tooling exceptions are detailed in [Validation.md](Validation.md). Native StoreKit simulations are not live sandbox certification.


## Unique passing test inventory

| Target / test method | Result | Latest listed evidence |
| --- | --- | --- |
| `BioPulsePurchaseUITests/SequentialAppSmokeTests/test08PaywallPurchaseAndRestoreForTargetApp` | Passed | `Final-BioPulse-Purchase.xcresult` |
| `BioPulsePurchaseUITests/SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro` | Passed | `SubscriptionButtons-BioPulse-Final.xcresult` |
| `ClausePurchaseUITests/SequentialAppSmokeTests/test08PaywallPurchaseAndRestoreForTargetApp` | Passed | `Production-ClauseShield-Purchase.xcresult` |
| `ClausePurchaseUITests/SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro` | Passed | `SubscriptionButtons-Clause-Final.xcresult` |
| `IndieSuiteEvaluationsTests/EntitlementConcurrencyTests/testMultipleWindowsShareFiveReservationsAndFailedWorkReleasesSlot` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/AppIntentsVerificationTests/structuredIntentResultsWithSeededLocalModels()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/authenticatedArchiveRoundTripAndWrongPassword()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/cloudCompatibleSchemaAndFullArchiveRecords()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/depreciationAndWarrantyDates()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/exactSuppliedPhenoAgeEquationAndMissingValues()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/historyDoesNotUseFutureReadings()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/receiptFactsOverrideUnsupportedModelValues()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/scannedImageOnlyPDFUsesOCR()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/syntheticDocumentsThroughLivePipeline()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/unitNormalization()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/FoundationModelsEvaluationTests/weightedRiskAndOmissionsAndDiff()` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/allRequiredMarkersRejectMissingNonfiniteAndNegativeValues()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/canonicalUnitAliasesAndEquivalentMeasurements()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/defensiveRiskBoundsAndProtectiveClauses()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/diffReconstructsBothVersionsWithRepeatedParagraphs()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/encryptedArchiveKeyMatchesPlatformPBKDF2()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/encryptedArchivesAuthenticateHeadersAndCiphertext()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/invalidVisionInputFailsCleanly()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/labAndContractArchivesPreserveAttachmentsAndDecisions()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/malformedAndIncompleteDocumentsDoNotInventFacts()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/multipagePDFRetainsFinalRecord()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/receiptTotalsExcludeSubtotalAndDatesAreValidated()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/ProductionRegressionTests/textAccentPaletteMaintainsContrastOnCardsAndBadges()` | Passed | `Final-Refinements.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/StoreKitVerificationTests/nineProductsAndVerifiedLifetimeEntitlements()` | Passed | `Final-Payment-EdgeCases.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/StoreKitVerificationTests/pendingDeclinedAndFailedPurchasesDoNotUnlock()` | Passed | `Final-Payment-EdgeCases.xcresult` |
| `IndieSuiteEvaluationsTests/IndieSuiteEvaluations/StoreKitVerificationTests/subscriptionExpiryAndLifetimeRefundRevokeAccess(bundle:)` | Passed | `Final-Payment-EdgeCases.xcresult` |
| `IndieSuiteUITests/AppIntentsVerificationTests/test01VaultIntentsAgainstLiveApp` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteUITests/AppIntentsVerificationTests/test02BioIntentAgainstLiveApp` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteUITests/AppIntentsVerificationTests/test03ClauseIntentAgainstLiveApp` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test01VaultGlassSeedAndLiveReceipt` | Passed | `Final-Vault-Source-Verification.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test02BioPulseSeedAndLiveLab` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test03ClauseShieldSeedAndLiveAudit` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test04CaptureLabStudioAndPrep` | Passed | `Final-iPad-Findings-LargeText.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test05CaptureContractReviewCards` | Passed | `Final-iPad-Findings-LargeText.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test06CaptureReceiptCoverageAndLedger` | Passed | `Final-iPad-Findings-LargeText.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test07BackupPoliciesAndBackgroundResumeAcrossApps` | Passed | `Final-Accessibility-Layout.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test08PaywallPurchaseAndRestoreForTargetApp` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test09EmptyInstallFlowsNeedNoAccountOrExternalFiles` | Passed | `Release-Candidate-Full.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test10MainScreenAccessibilityAudit` | Passed | `Final-iPad-Findings-LargeText.xcresult` |
| `IndieSuiteUITests/SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro` | Passed | `Adaptive-Layout-And-Plans.xcresult` |

## Result bundles and repeat executions

## Release-Candidate-Full.xcresult

Result: **Passed**. 40 passed, 0 failed, 0 skipped.

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
| `IndieSuiteEvaluations/StoreKitVerificationTests/subscriptionExpiryAndLifetimeRefundRevokeAccess(bundle:)` | Passed |
| `IndieSuiteEvaluations/StoreKitVerificationTests/pendingDeclinedAndFailedPurchasesDoNotUnlock()` | Passed |
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
| `SequentialAppSmokeTests/test08PaywallPurchaseAndRestoreForTargetApp()` | Passed |
| `SequentialAppSmokeTests/test09EmptyInstallFlowsNeedNoAccountOrExternalFiles()` | Passed |
| `SequentialAppSmokeTests/test10MainScreenAccessibilityAudit()` | Passed |

Local evidence: `TestResults/Release-Candidate-Full.xcresult`.

## Final-Refinements.xcresult

Result: **Passed**. 18 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
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
| `IndieSuiteEvaluations/StoreKitVerificationTests/subscriptionExpiryAndLifetimeRefundRevokeAccess(bundle:)` | Passed |
| `IndieSuiteEvaluations/StoreKitVerificationTests/pendingDeclinedAndFailedPurchasesDoNotUnlock()` | Passed |
| `SequentialAppSmokeTests/test05CaptureContractReviewCards()` | Passed |
| `SequentialAppSmokeTests/test06CaptureReceiptCoverageAndLedger()` | Passed |
| `SequentialAppSmokeTests/test10MainScreenAccessibilityAudit()` | Passed |

Local evidence: `TestResults/Final-Refinements.xcresult`.

## Final-Payment-EdgeCases.xcresult

Result: **Passed**. 3 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `IndieSuiteEvaluations/StoreKitVerificationTests/nineProductsAndVerifiedLifetimeEntitlements()` | Passed |
| `IndieSuiteEvaluations/StoreKitVerificationTests/subscriptionExpiryAndLifetimeRefundRevokeAccess(bundle:)` | Passed |
| `IndieSuiteEvaluations/StoreKitVerificationTests/pendingDeclinedAndFailedPurchasesDoNotUnlock()` | Passed |

Local evidence: `TestResults/Final-Payment-EdgeCases.xcresult`.

## Final-BioPulse-Purchase.xcresult

Result: **Passed**. 1 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test08PaywallPurchaseAndRestoreForTargetApp()` | Passed |

Local evidence: `TestResults/Final-BioPulse-Purchase.xcresult`.

## Production-ClauseShield-Purchase.xcresult

Result: **Passed**. 1 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test08PaywallPurchaseAndRestoreForTargetApp()` | Passed |

Local evidence: `TestResults/Production-ClauseShield-Purchase.xcresult`.

## Adaptive-Layout-And-Plans.xcresult

Result: **Passed**. 3 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test04CaptureLabStudioAndPrep()` | Passed |
| `SequentialAppSmokeTests/test06CaptureReceiptCoverageAndLedger()` | Passed |
| `SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro()` | Passed |

Local evidence: `TestResults/Adaptive-Layout-And-Plans.xcresult`.

## SubscriptionButtons-BioPulse-Final.xcresult

Result: **Passed**. 1 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro()` | Passed |

Local evidence: `TestResults/SubscriptionButtons-BioPulse-Final.xcresult`.

## SubscriptionButtons-Clause-Final.xcresult

Result: **Passed**. 1 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test11MonthlyAndAnnualSubscriptionButtonsUnlockPro()` | Passed |

Local evidence: `TestResults/SubscriptionButtons-Clause-Final.xcresult`.

## Final-Accessibility-Layout.xcresult

Result: **Passed**. 5 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test04CaptureLabStudioAndPrep()` | Passed |
| `SequentialAppSmokeTests/test05CaptureContractReviewCards()` | Passed |
| `SequentialAppSmokeTests/test06CaptureReceiptCoverageAndLedger()` | Passed |
| `SequentialAppSmokeTests/test07BackupPoliciesAndBackgroundResumeAcrossApps()` | Passed |
| `SequentialAppSmokeTests/test10MainScreenAccessibilityAudit()` | Passed |

Local evidence: `TestResults/Final-Accessibility-Layout.xcresult`.

## Chart-Final-Light.xcresult

Result: **Passed**. 1 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test04CaptureLabStudioAndPrep()` | Passed |

Local evidence: `TestResults/Chart-Final-Light.xcresult`.

## Chart-Final-LargeText.xcresult

Result: **Passed**. 1 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test04CaptureLabStudioAndPrep()` | Passed |

Local evidence: `TestResults/Chart-Final-LargeText.xcresult`.

## Final-Vault-Source-Verification.xcresult

Result: **Passed**. 3 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test01VaultGlassSeedAndLiveReceipt()` | Passed |
| `SequentialAppSmokeTests/test06CaptureReceiptCoverageAndLedger()` | Passed |
| `SequentialAppSmokeTests/test10MainScreenAccessibilityAudit()` | Passed |

Local evidence: `TestResults/Final-Vault-Source-Verification.xcresult`.

## Final-iPad-Findings-Regression.xcresult

Result: **Passed**. 4 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test04CaptureLabStudioAndPrep()` | Passed |
| `SequentialAppSmokeTests/test05CaptureContractReviewCards()` | Passed |
| `SequentialAppSmokeTests/test06CaptureReceiptCoverageAndLedger()` | Passed |
| `SequentialAppSmokeTests/test10MainScreenAccessibilityAudit()` | Passed |

Local evidence: `TestResults/Final-iPad-Findings-Regression.xcresult`.

## Final-iPad-Findings-LargeText.xcresult

Result: **Passed**. 4 passed, 0 failed, 0 skipped.

| Test | Result |
| --- | --- |
| `SequentialAppSmokeTests/test04CaptureLabStudioAndPrep()` | Passed |
| `SequentialAppSmokeTests/test05CaptureContractReviewCards()` | Passed |
| `SequentialAppSmokeTests/test06CaptureReceiptCoverageAndLedger()` | Passed |
| `SequentialAppSmokeTests/test10MainScreenAccessibilityAudit()` | Passed |

Local evidence: `TestResults/Final-iPad-Findings-LargeText.xcresult`.

