# Validation status

The apps are **not yet certified ready for production**. Automated simulator checks have passed in the recorded scopes below, but physical-device QA, real App Store sandbox testing, live-service validation and domain review remain release gates. No hardware testing or physical-device recording is represented as complete.

## Completed automated evidence

See [the test-by-test results](TestResults.md). **45 distinct target-qualified test methods passed**: 27 core/evaluation methods, 14 main UI/App Intents methods, and two purchase UI methods for each additional app host. Repeated executions do not inflate this count; the subscription expiry method also runs with three app parameters. The baseline complete result bundle passed 40 methods with zero failures/skips; later focused bundles cover new tests and final changes. Each bundle's exact scope is listed in the report, rather than claiming that the baseline ran later changes.

Final refinements passed normal light-mode and dark/accessibility XXXL checks, including marker selection, contract decisions, receipt detail, background/resume, landscape and visible-body accessibility checks. Native monthly, annual, lifetime and restore UI paths passed for all three app hosts. StoreKit pending, decline, network failure, user cancellation, retry and subsequent Ask to Buy approval were verified; approval updates the existing entitlement manager without relaunch.

All functional regression tests use the same iPhone 17e simulator, iOS 27.0, UDID `CEAF94B4-5BB2-46B3-A7B5-B075AB0098BC`. Parallel testing and destination cloning are disabled. UI workflows terminate each app before launching the next. Local Xcode result bundles retain the underlying logs and screenshots; the public repository contains this report rather than private machine logs.

## Issues found and corrected

- Backgrounding called UIKit's state-restoration extension outside a valid transition and caused a SIGTRAP. All three SwiftUI scenes now use native automatic restoration and preserve their selected tab. The three-app background/resume and landscape regression passed.
- Receipt totals could match “Subtotal” and date extraction supported only ISO dates. Total extraction now matches explicit total labels, prefers grand total, validates thousands/decimal grouping, and rejects unsupported currency labels and nonfinite amounts. U.S. slash dates, unambiguous day-first dates, year-first dates and English month names are normalized and calendar-validated. USD and ambiguous numeric-date assumptions are disclosed on the receipt detail screen.
- Receipt model output could substitute unsupported facts. Reconciliation now anchors total, date, serial and coverage terms to source extraction; regression tests reject unsupported prices, dates and identifiers. Missing policy terms retain the specified 30-day return/12-month warranty estimates and require policy verification; this is not a claim that absent terms were extracted from the receipt.
- An earlier entitlement refresh could overwrite a newer result. Refresh generation ordering prevents stale snapshots; lifetime verification and subscription expiration/refund checks passed.
- Encrypted archive headers were not authenticated. Format 2 includes the app identifier in AES-GCM authenticated data and rejects altered headers, ciphertext and malformed salts. Unreleased format 1 QA archives are deliberately unsupported.
- Contract scoring now bounds hostile integer inputs, normalizes severity labels and avoids flagging plainly protective retained-IP/non-compete wording. Unsupported quotations and duplicates are reconciled against source text.
- The audit identified faint secondary captions and native section headers. They now use readable adaptive colors. Currency summaries expose descriptive accessibility labels and values in US dollars. Native Pro controls use the system label tint; rendered text/backdrop contrast measured approximately 18.7:1 in the normal light-mode run. The body audit passed across three scrolled viewports per app, with the scope described below.
- Earlier accessibility workflow attempts encountered offscreen controls and brittle element queries. The automated clipping audit also flagged an item title on a partially visible scrolling card; its full text is readable in the captured viewport, so clipping remains a screenshot/hardware review scope while automated audits cover contrast and element descriptions. Those failures are retained locally. Corrected locators and the adaptive layouts passed the final large-text run. Manual screenshot review found and corrected a marker-picker overlap that control-existence checks alone had missed.

The final selected-sidebar, valuation-announcement and named-marker changes passed four focused tests in normal light mode and four in dark/accessibility XXXL mode. The last display-value helper refactor also passed live receipt extraction, coverage/ledger and three-app visible-content checks before those final changes. Exact bundle scopes are listed in the test report.

All final signed archives and production exports pass for VaultGlass build 2, BioPulse build 3 and ClauseShield build 2; see [package verification and fingerprints](BuildVerification.md). Apple initially rejected BioPulse for a missing HealthKit update purpose string despite read-only authorization. Both Health purpose strings are now present and checked before archiving. Upload/processing is recorded in the submission status.

The 13-inch iPad capture also confirmed the corrected selected risk badge and separate spoken valuation elements. Capture profiles ran individually after the functional test simulator was shut down; this is visual/capture coverage, not a second complete functional regression matrix.

## Compilation and release limits

All three final Release archives and App Store distribution exports passed. Deep/strict code-signature verification, app identities, version/minimum OS, privacy manifests and required capabilities passed. Exported packages have get-task-allow disabled, production push and production iCloud entitlements; VaultGlass includes the signed widget and its App Group privacy reason. This validates package construction, not runtime behavior on hardware. Debug QA controls and entitlement overrides are excluded from Release.

The simulator exercises model generation when available and deterministic fallback when unavailable or over budget. It does not certify model quality across every device, language or region. Lab reference intervals are illustrative; the supplied PhenoAge equation and legal screening rules require qualified domain review before public release.

Physical-device checks must cover camera/OCR, HealthKit authorized/denied/no-data behavior, real notifications, widget updates, model availability/performance, large-document memory, CloudKit synchronization and production schema, Release/TestFlight purchases and restore, and iPad/window/accessibility behavior. Follow [OnDeviceQA.md](OnDeviceQA.md) and provide the physical launch-to-flow recording requested under Guideline 2.1.

## Accessibility audit scope and tooling exceptions

The final visible-content accessibility tests passed in normal light mode and dark/accessibility XXXL mode. The test checks contrast and sufficient element descriptions in three scrolled dashboard viewports for each app, using an isolated in-memory demo fixture. It independently checks the rendered pixels of each native Pro control against a 4.5:1 threshold.

iOS 27's native toolbar contrast audit flags that control even when the captured text is black on a light backdrop. Only that measured native control is handled as a tooling exception. Contrast reports for nodes outside the fully visible content rectangle (under floating navigation/tab bars, or partly offscreen horizontally) are deferred to visible viewports. The test does not represent those occluded pixels as readable content. Clipping is reviewed through the separate large-text screenshots rather than claiming a clean automated clipping audit. These checks do not certify full VoiceOver usability or every app screen; supported physical-device accessibility QA remains required.
