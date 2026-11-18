# Repair extraction regression results

Two selected methods passed with zero failures or skips on one iPhone 17e simulator running iOS 27.0 on 18 November 2026. Xcode 27.2 ran the methods sequentially with parallel testing disabled and two build jobs. Application and regression source: `caf36ab`.

| Method in `SequentialWorkspaceQASuite` | Result | Coverage |
| --- | --- | --- |
| `test10_RepairGenerationPreservesQuotedFactsAndSafetyTriage()` | Passed | Injects a generated whole-price-line service name, incorrect safety category, changed price, mismatched source quote and omitted item. Each must recover the exact quoted brake service, prices and safety category; a fully grounded generated note remains accepted. |
| `test07_TorqueShield_VINCheckDigitAndEstimateRedliner()` | Passed | Full repair import with exact brake service/prices/safety triage, inverse relationships, finite nonnegative costs, unknown independent benchmark, initial review decision, VIN and lease calculations, PDF generation and sequential smoke pipeline. |

The end-to-end method uses an isolated in-memory model context and releases its fixtures and transient inference caches. It does not certify CloudKit synchronization. Result root: `TestResults/Repair-Grounding-20261118-213519`.

The preceding fresh-install UI pass revealed that a local model could return a whole itemized line as the service name and label brake work as routine maintenance. Four other app flows passed; the TorqueShield case failed and is retained in `TestResults/Batch2-Normal-Launch-20261118-210637/iPhone.xcresult`. That failed case is not counted as a pass. The fix reconciles generated services, prices, source lines and safety categories against the source-based extraction before saving an audit. The clean full UI retest subsequently passed all five flows on both profiles. The readable repair-label update passed its flow again on each profile; see the [current UI report](Batch2UIResults.md).
