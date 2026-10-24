# Eight-app sequential QA results

**All eight app schemes passed; nine distinct app/mode test methods passed, with no failures or skips in the listed bundles.** This does not establish physical-device, live-purchase, printing-hardware or production-cloud readiness.

The CLI reused one iOS 27.0 iPhone 17e. Parallel tests/clones were disabled. Each scheme completed before the next began; only its disposable app caches/tmp were cleared. In-memory records were deleted through registered contexts and shared inference/source caches were purged.

| App | Passing method | Evidence |
| --- | --- | --- |
| VaultGlass | `SequentialWorkspaceQASuite/test01_VaultGlass_EndToEndAndDepreciation()` | `TestResults/Sequential-8-App-20261024-110537/VaultGlass.xcresult` |
| BioPulseLocal | `SequentialWorkspaceQASuite/test02_BioPulseLocal_UnitNormalizationAndPhenoAge()` | `TestResults/Sequential-8-App-20261024-110537/BioPulseLocal.xcresult` |
| ClauseShield | `SequentialWorkspaceQASuite/test03_ClauseShield_RiskScoringAndVersionDiff()` | `TestResults/Sequential-8-App-20261024-110537/ClauseShield.xcresult` |
| DeductGlass | `SequentialWorkspaceQASuite/test04_DeductGlass_DualMethodTaxOptimizerAndAuditBinder()` | `TestResults/Sequential-8-App-20261024-110537/DeductGlass.xcresult` |
| EchoBrief | `SequentialWorkspaceQASuite/test05_EchoBrief_MeetingBurnRateAndCommitmentExtraction()` | `TestResults/Sequential-8-App-20261024-110537/EchoBrief.xcresult` |
| NutriLoupe | `SequentialWorkspaceQASuite/test06_NutriLoupe_NOVAScorerAndBayesianTriggerRanker()` | `TestResults/Sequential-8-App-20261024-110537/NutriLoupe.xcresult` |
| TorqueShield | `SequentialWorkspaceQASuite/test07_TorqueShield_VINCheckDigitAndEstimateRedliner()` | `TestResults/Sequential-8-App-20261024-110537/TorqueShield.xcresult` |
| RecallGlass | `SequentialWorkspaceQASuite/test08_RecallGlass_AcademicFSRS5AndSemanticGrader()` | `TestResults/RecallGlass-Final-Anchors.xcresult` |
| RecallGlass | `SequentialWorkspaceQASuite/test09_RecallGlass_CorporateSpeechToCueCardCutoutPDFImposition()` | `TestResults/RecallGlass-Final-Anchors.xcresult` |

## Recorded smoke measurements

These are individual observations, not performance guarantees. The memory field is the maximum **sampled host resident-memory increase** at 20 ms intervals. It excludes the separate model service and can miss shorter peaks. MetricKit reports arrive later and are not misrepresented as immediate per-test measurements.

| Target | Duration, ms | Sampled memory increase, MB | Assertions passed |
| --- | ---: | ---: | ---: |
| vaultGlass | 1922.7 | 1.48 | 4 |
| bioPulseLocal | 5169.9 | 1.62 | 4 |
| clauseShield | 2402.9 | 1.59 | 4 |
| deductGlass | 3939.2 | 1.84 | 5 |
| echoBrief | 5935.6 | 1.31 | 5 |
| nutriLoupe | 3381.4 | 1.48 | 5 |
| torqueShield | 6137.7 | 1.80 | 5 |
| recallGlassAcademic | 6347.5 | 1.59 | 5 |
| recallGlassCorporateSpeech | 5954.7 | 0.30 | 6 |

## Scope

The suite checks real synthetic input/PDF ingestion, generative-or-validated-fallback extraction, in-memory persistence, deterministic domain calculations and boundaries, and readable PDF output. RecallGlass tests all six card/paper combinations, media boxes, headers/pause text, represented-word pacing, reorder timing/next-card transitions, eight-card pagination at three type scales, and oversized body/footer rejection. All twelve exported PDF samples (28 pages) were rendered and visually reviewed; see [native print samples](Previews/Batch2/PrintSamples/README.md). App-specific Batch 1 regression suites remain separate. Interactive UI-flow results are reported separately.

## Retained failed attempts

Earlier runs exposed a 2048-pixel icon generation error, an unsupported model quote, and a SwiftData contract violation from erasing a still-registered store. Those failures were retained privately and are not counted above. The icon generator now produces opaque 1024-pixel assets, source quotations can be validated before accepting a model response, and cleanup deletes records through live contexts. Subsequent results must be rerun when the relevant implementation changes.
