# Physical-device test results

Device: iPhone 18 Pro Max, iOS 27.2 beta (24B115). Tests ran sequentially on one connected phone on 24 October 2026 (Hong Kong). Parallel execution was disabled. No skipped, failed, interrupted or setup-only attempt is counted as a product pass.

**35 distinct physical test methods passed: 25 hardware data-processing tests and 10 installed-app UI flows.** Hardware domain tests overlap simulator coverage; counts must not be summed as if every execution were a new method. Repeated UI recordings do not increase the physical-method count.

Installed-app UI tests drove TestFlight version 1.0.0: VaultGlass build 2, BioPulse Local build 5, ClauseShield build 2 in the latest bundles. Earlier BioPulse builds 3 and 4 remain historical evidence and are identified separately below. The owner confirmed TestFlight installation; App Store Connect reported the authorized internal tester as INSTALLED for all three. The independent UI host has no app-target dependency, QA launch arguments or StoreKit test configuration. Hardware computation tests compile the same domain sources at the tested source revision in a separate test host; they are distinguished from testing installed app binaries.

| Test | Result | Latest passing evidence |
| --- | --- | --- |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/authenticatedArchiveRoundTripAndWrongPassword()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/cloudCompatibleSchemaAndFullArchiveRecords()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/depreciationAndWarrantyDates()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/exactSuppliedPhenoAgeEquationAndMissingValues()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/historyDoesNotUseFutureReadings()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/receiptFactsOverrideUnsupportedModelValues()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/scannedImageOnlyPDFUsesOCR()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/syntheticDocumentsThroughLivePipeline()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/unitNormalization()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/FoundationModelsEvaluationTests/weightedRiskAndOmissionsAndDiff()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/HardwareTelemetryTests/receiptPipelineRecordsActualModelRoute()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/HardwareTelemetryTests/tenPageImageOnlyPDFRetainsEveryPage()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/allRequiredMarkersRejectMissingNonfiniteAndNegativeValues()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/canonicalUnitAliasesAndEquivalentMeasurements()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/defensiveRiskBoundsAndProtectiveClauses()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/diffReconstructsBothVersionsWithRepeatedParagraphs()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/encryptedArchiveKeyMatchesPlatformPBKDF2()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/encryptedArchivesAuthenticateHeadersAndCiphertext()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/invalidVisionInputFailsCleanly()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/labAndContractArchivesPreserveAttachmentsAndDecisions()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/malformedAndIncompleteDocumentsDoNotInventFacts()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/multipagePDFRetainsFinalRecord()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/physicianPreparationAlwaysHasFiveDistinctQuestions()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/receiptTotalsExcludeSubtotalAndDatesAreValidated()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `IndieSuiteEvaluations/ProductionRegressionTests/textAccentPaletteMaintainsContrastOnCardsAndBadges()` | Passed | `Physical-Hardware-Core-Grounded-Questions.xcresult` |
| `PhysicalReleaseFlowTests/test01VaultGlassInstalledReleasePersistenceAndCoverage()` | Passed | `Physical-VaultGlass-Flow-6.xcresult` |
| `PhysicalReleaseFlowTests/test02BioPulseInstalledReleasePanelChartAndDoctorBrief()` | Passed | `Physical-TestFlight-Pro-Bio5-Verified.xcresult` |
| `PhysicalReleaseFlowTests/test03ClauseShieldInstalledReleaseSavedDecisionAndDraft()` | Passed | `Physical-ClauseShield-Flow-3.xcresult` |
| `PhysicalReleaseFlowTests/test04VaultGlassNewReceiptAndInsurancePDF()` | Passed | `Physical-Final-Vault-Clause-Launch.xcresult` |
| `PhysicalReleaseFlowTests/test05BioPulseDoctorPDFAndChartText()` | Passed | `Physical-TestFlight-Pro-Bio5-Verified.xcresult` |
| `PhysicalReleaseFlowTests/test06ClauseShieldImportReviewDraftAndPDF()` | Passed | `Physical-Final-Vault-Clause-Launch.xcresult` |
| `PhysicalReleaseFlowTests/test07BioPulseFreshImportChartAndDoctorFlow()` | Passed | `Physical-TestFlight-Pro-Bio5-Verified.xcresult` |
| `PhysicalReleaseFlowTests/test08VaultGlassActiveLifetimeAndPaidAnalysis()` | Passed | `Physical-TestFlight-Pro-Bio5-Verified.xcresult` |
| `PhysicalReleaseFlowTests/test09ClauseShieldActiveLifetimeAndPaidReview()` | Passed | `Physical-TestFlight-Pro-Bio5-Verified.xcresult` |
| `PhysicalReleaseFlowTests/test10BioPulseActiveLifetimeAndPaidWorkspace()` | Passed | `Physical-TestFlight-Pro-Bio5-Verified.xcresult` |

## Completed bundles

| Bundle | Passed | Failed | Skipped |
| --- | --- | --- | --- |
| `Physical-Hardware-Core-Grounded-Questions.xcresult` | 25 | 0 | 0 |
| `Physical-VaultGlass-Flow-6.xcresult` | 1 | 0 | 0 |
| `Physical-ClauseShield-Flow-3.xcresult` | 1 | 0 | 0 |
| `Physical-Final-Recordings-And-Exports.xcresult` | 4 | 0 | 0 |
| `Physical-BioPulse-Build4-Retry2.xcresult` | 3 | 0 | 0 |
| `Physical-Final-Vault-Clause-Launch.xcresult` | 2 | 0 | 0 |
| `Physical-TestFlight-Pro-Bio5-Verified.xcresult` | 6 | 0 | 0 |

## Hardware observations

- Earlier hardware run: actual on-device model route was available and used for receipt, blood-panel and contract evaluations; those inference logs reported fallback false.
- Earlier hardware run, separate receipt inference: 6,153 ms; resident memory after inference 210.8 MB; model available; fallback unused. This is one observation, not peak memory, a percentile or a universal performance guarantee.
- Earlier hardware run, ten-page image-only receipt PDF: all ten serial-number occurrences recovered; 1.33 seconds for the measured OCR operation; 114,230-byte input.
- Receipt import generated the expected USD 2,499 price and C02X9876Q6L4 serial. Notification access was declined; later completed receipt/persistence tests passed.
- Insurance, doctor-brief and contract-comparison PDFs rendered on the phone. The lab text alternative exposed the expected 4.6 g/dL Albumin value.
- Contract replacement decisions were visible after terminating and reopening the installed app. All three main UI flows passed background/resume checks.

## Scope and retained failures

Early physical attempts encountered first-launch TestFlight instructions, the notification prompt and test queries that assumed incorrect document titles, modal navigation or uncombined accessibility labels. Those bundles are retained privately and excluded above. Runner setup originally timed out awaiting owner authentication. The successful Control Center setup check is also excluded from the product-test count. Hardware review revealed that BioPulse retained only two physician questions. Build 4 fixed the count; subsequent screenshot review caught unsupported high/low premises despite passing UI assertions. Build 5 replaces unvalidated prose with neutral questions composed from verified marker identities, including restored panels. Current installed-app tests verify the neutral Albumin question and fifth question alongside chart, PDF and persistence behavior. Setup and harness failures remain excluded.

Native Control Center recordings show the actual installed apps and synthetic documents. Raw recordings and hardware identifiers remain private. Review copies retain native 1320 × 2868 pixels, trim outer recording setup/cleanup and use HEVC; they contain continuous app interactions without simulated app screens. The owner activated lifetime access in all three apps. Installed-app Pro checks verify active access, relaunch persistence and paid-feature use without QA entitlement overrides. TestFlight service behavior is distinguished from the local StoreKit simulation. Current Pro recordings require independent visual/privacy review before publication. See [physical captures and recordings](Previews/Physical-TestFlight/README.md).

These passes do not certify live StoreKit transactions, physical iPad, public stable OS, unavailable-model hardware behavior, camera permissions, production CloudKit/two-device sync, every accessibility mode, peak-memory stress, clinical/legal content or App Review approval. See [remaining release gates](ProductionReadiness.md).
