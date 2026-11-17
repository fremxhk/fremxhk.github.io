# Eight-app sequential QA results

**All eight app schemes passed; nine distinct app/mode test methods passed, with no failures or skips in the listed bundles.** This does not establish physical-device, live-purchase, printing-hardware or production-cloud readiness.

The CLI reused one iOS 27.0 iPhone 17e. Parallel tests/clones were disabled. Each scheme completed before the next began; only its disposable app caches/tmp were cleared. In-memory records were deleted through registered contexts and shared inference/source caches were purged.

| App | Passing method | Evidence |
| --- | --- | --- |
| VaultGlass | `SequentialWorkspaceQASuite/test01_VaultGlass_EndToEndAndDepreciation()` | `TestResults/Sequential-8-App-20261117-201658/VaultGlass.xcresult` |
| BioPulseLocal | `SequentialWorkspaceQASuite/test02_BioPulseLocal_UnitNormalizationAndPhenoAge()` | `TestResults/Sequential-8-App-20261117-201658/BioPulseLocal.xcresult` |
| ClauseShield | `SequentialWorkspaceQASuite/test03_ClauseShield_RiskScoringAndVersionDiff()` | `TestResults/Sequential-8-App-20261117-201658/ClauseShield.xcresult` |
| DeductGlass | `SequentialWorkspaceQASuite/test04_DeductGlass_DualMethodTaxOptimizerAndAuditBinder()` | `TestResults/Sequential-8-App-20261117-201658/DeductGlass.xcresult` |
| EchoBrief | `SequentialWorkspaceQASuite/test05_EchoBrief_MeetingBurnRateAndCommitmentExtraction()` | `TestResults/Sequential-8-App-20261117-201658/EchoBrief.xcresult` |
| NutriLoupe | `SequentialWorkspaceQASuite/test06_NutriLoupe_NOVAScorerAndBayesianTriggerRanker()` | `TestResults/Sequential-8-App-20261117-201658/NutriLoupe.xcresult` |
| TorqueShield | `SequentialWorkspaceQASuite/test07_TorqueShield_VINCheckDigitAndEstimateRedliner()` | `TestResults/Sequential-8-App-20261117-201658/TorqueShield.xcresult` |
| RecallGlass | `SequentialWorkspaceQASuite/test08_RecallGlass_AcademicFSRS5AndSemanticGrader()` | `TestResults/Sequential-8-App-20261117-201658/RecallGlass.xcresult` |
| RecallGlass | `SequentialWorkspaceQASuite/test09_RecallGlass_CorporateSpeechToCueCardCutoutPDFImposition()` | `TestResults/Sequential-8-App-20261117-201658/RecallGlass.xcresult` |

## Recorded smoke measurements

These are individual observations, not performance guarantees. The memory field is the maximum **sampled host resident-memory increase** at 20 ms intervals. It excludes the separate model service and can miss shorter peaks. MetricKit reports arrive later and are not misrepresented as immediate per-test measurements.

| Target | Duration, ms | Sampled memory increase, MB | Assertions passed |
| --- | ---: | ---: | ---: |
| vaultGlass | 5130.5 | 1.61 | 4 |
| bioPulseLocal | 2323.7 | 31.27 | 4 |
| clauseShield | 8239.8 | 9.41 | 4 |
| deductGlass | 9899.0 | 3.02 | 5 |
| echoBrief | 15196.8 | 2.41 | 5 |
| nutriLoupe | 8944.9 | 0.84 | 5 |
| torqueShield | 12829.3 | 1.28 | 5 |
| recallGlassAcademic | 15651.0 | 2.88 | 5 |
| recallGlassCorporateSpeech | 10378.8 | 0.56 | 6 |

## Scope

The suite checks real synthetic input/PDF ingestion, generative-or-validated-fallback extraction, in-memory persistence, deterministic domain calculations and boundaries, and readable PDF output. RecallGlass tests all six card/paper combinations, media boxes, headers/pause text, represented-word pacing, reorder timing/next-card transitions, eight-card pagination at three type scales, and oversized body/footer rejection. Twelve separately retained PDF samples (28 pages) were rendered and visually reviewed during earlier PDF validation; see [native print samples](Previews/Batch2/PrintSamples/README.md). This rerun checks generated PDF text, media boxes and pagination programmatically; it does not relabel the prior visual review as new evidence. App-specific Batch 1 regression suites remain separate. Interactive UI-flow results are reported separately.

## Retained failed attempts

Earlier runs exposed a 2048-pixel icon generation error, an unsupported model quote, and a SwiftData contract violation from erasing a still-registered store. Those failures were retained privately and are not counted above. The icon generator now produces opaque 1024-pixel assets, source quotations can be validated before accepting a model response, and cleanup deletes records through live contexts. On 17 November 2026 a fresh run was interrupted by exhausted disk space. Its repair smoke path also exposed use of the study prompt without a grounding validator. The harness now uses the mechanic prompt and rejects empty or unsupported quotes before accepting generated output, retaining the assertion and deterministic fallback. These failed/interrupted bundles are excluded. Subsequent results must be rerun when the relevant implementation changes.
