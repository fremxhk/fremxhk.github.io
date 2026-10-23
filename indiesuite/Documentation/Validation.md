# Validation record

Verified 23 October 2026 with Xcode 27.1 (27A9275), Swift 6.4, the iOS 27.1 SDK, and an iPhone 17e simulator running iOS 27.0.

## Automated checks

Eighteen distinct checks passed across the core evaluation suite (11), quota regression (1), and Siri/UI suite (6). Targeted rechecks after the final changes also passed. The table records the successful result bundles; repeat runs do not increase the distinct-check count.

| Scope | Result | Evidence |
| --- | --- | --- |
| Core evaluation suite | 11 passed | [Evaluations.xcresult](../TestResults/20261023-021649/Evaluations.xcresult) |
| Live Siri and app workflows | 6 passed | [Workflow-Final.xcresult](../TestResults/Workflow-Final.xcresult) |
| Multi-window quota regression | 1 passed | [Quota-Regression.xcresult](../TestResults/Quota-Regression.xcresult) |
| Risk scoring / duplicate findings regression | 1 passed | [Risk-Deduplication.xcresult](../TestResults/Risk-Deduplication.xcresult) |
| Final BioPulse and ClauseShield workflow recheck | 2 passed | [FocusedUI-Final.xcresult](../TestResults/FocusedUI-Final.xcresult) |
| Final ClauseShield reconciliation workflow | 1 passed | [Clause-Deduplication.xcresult](../TestResults/Clause-Deduplication.xcresult) |
| Repeatable workflows and clean UI captures | 3 passed | [CleanPreviews.xcresult](../TestResults/CleanPreviews.xcresult) |

Every simulator run used CEAF94B4-5BB2-46B3-A7B5-B075AB0098BC. Simulator parallel testing was disabled, the Swift Testing parent suite was serialized, and app UI tests terminated one app before launching the next. No test was skipped in the successful recorded scopes.

The core suite exercised real document text extraction, Vision OCR (including a scanned image-only PDF), guided FoundationModels generation or deterministic fallback, exact unit normalization, the supplied PhenoAge equation, depreciation, warranty dates, risk scoring, omission checks, paragraph diffing, authenticated archive round trips and incorrect-password handling, SwiftData schema creation, all nine StoreKit products, annual trial metadata and verified lifetime entitlements. A separate quota regression verified five shared reservations across two manager instances and release of a canceled slot. A later workflow repeat also reached the persisted five-use limit and correctly opened the paywall; workflow setup now explicitly selects the existing Debug Pro override, so those tests remain repeatable without erasing device data. The quota regression does not use that override.

Live AppIntentsTesting ran from the UI bundle against each installed app. The UI workflows seeded history, analyzed synthetic documents, opened the result screens, and accepted a contract counter-clause before opening the negotiation draft. Native screenshots were exported and visually reviewed; copies are in [Previews](Previews).

## Device compilation

All three app schemes passed an unsigned arm64 Release build for generic iOS devices. VaultGlass's widget built with its host app. After the final contract reconciliation change, ClauseShield's Release build passed again. All three Release builds passed once more after generating and visually checking the final original geometric app icons. Generated app metadata was checked for the requested bundle identifiers, iOS 27.0 minimum, scene manifests and launch-screen declarations. Project preflight verified capability files and the nine product identifiers.

Debug QA controls and entitlement overrides are excluded from Release. Push environment is development for Debug and production for Release. The Xcode project and shared schemes are included and require no XcodeGen installation to open.

## Practical limits

No physical-device deployment or hardware QA was performed. Developer-team signing and capability provisioning remain necessary before installing the apps on a phone or iPad. Real CloudKit synchronization, camera capture, HealthKit data authorization, notification delivery, hardware model availability and App Store sandbox lifecycle behavior must be checked using [OnDeviceQA.md](OnDeviceQA.md).

The simulator demonstrated both a successful model response and the bounded deterministic fallback when later model responses exceeded the 45-second budget. It does not certify model output quality on every device or region. Lab ranges are explicitly illustrative QA intervals and legal playbooks are screening rules; domain review remains a release gate.

Earlier development failures are retained in ignored TestResults folders for diagnosis. The successful scopes above supersede their corresponding checks. No deployment, App Store publication or CloudKit production-schema promotion was performed.
