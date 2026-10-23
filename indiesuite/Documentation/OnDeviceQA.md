# On-device QA walkthrough

## Prepare Xcode signing

1. Open `IndieSuite.xcworkspace` in Xcode 27.0 or newer, using Swift 6.4.
2. Select your Apple Developer team for all three apps and the widget. The build can use an external signing configuration; private credentials are excluded from Git.
3. Register the requested bundle identifiers and private CloudKit containers:

| App | Bundle | CloudKit container |
| --- | --- | --- |
| VaultGlass | com.indiesuite.vaultglass | iCloud.com.indiesuite.vaultglass |
| BioPulse Local | com.indiesuite.biopulselocal | iCloud.com.indiesuite.biopulselocal |
| ClauseShield | com.indiesuite.clauseshield | iCloud.com.indiesuite.clauseshield |

4. Enable the VaultGlass app group `group.com.indiesuite.vaultglass` for the app and widget. Enable HealthKit for BioPulse Local, CloudKit and push notifications for the three apps. CloudKit requires a developer team supporting that capability. Let automatic signing create compatible profiles.
5. In each scheme's Run options, confirm `IndieSuiteProducts.storekit` is selected. Xcode must launch the Debug app for local StoreKit testing. No production App Store purchase is required for QA.
6. Attach an iOS 27 iPhone or iPad, trust the computer, enable Developer Mode, and run each app separately. Check a signed-out-iCloud device as well as a signed-in device.

## Simulator protocol

Run `Scripts/test-sequential.sh SIMULATOR_UDID` against one already booted simulator. The script installs apps sequentially, then runs evaluations, then the main UI tests, then the two additional app-specific purchase hosts. UI tests terminate one app before launching the next. Simulator parallel testing and destination cloning are disabled; the Swift Testing parent suite is serialized. Do not run multiple copies of the script at once.

## Shared checks, in each app

- [ ] Cold launch with no files and no network; empty state appears without a crash.
- [ ] Open QA, tap **Seed Full Demo Database**, and verify six historical records. Repeat seeding and check that historical demo records are not duplicated.
- [ ] Tap **Run Live AI Pipeline on Synthetic Sample**. Confirm the generated binary image/PDF passes through extraction and opens a real result screen.
- [ ] Open telemetry. Record model availability, fallback reason, elapsed milliseconds and resident memory. MetricKit system payloads may take a day to arrive; the view does not fabricate them.
- [ ] Test an Apple Intelligence capable device with its model ready, and an unavailable/unsupported configuration. Both routes must yield usable, source-grounded results or an actionable input error.
- [ ] Switch QA entitlement among Free, Pro and Exhausted. Exhausted blocks analysis and opens/points to Pro; Pro allows analysis. Restore Live before testing real quota persistence.
- [ ] In Live mode, complete five actions, relaunch, and check that a sixth action is blocked. Failed extraction should not consume quota. Check storage failure behavior on a protected/locked device.
- [ ] Buy monthly, annual and lifetime via local StoreKit; verify the seven-day annual introductory offer. Test cancellation, pending approval, refund/revocation and Restore Purchases with Xcode's transaction manager. Check no unlock occurs for unverified transactions.
- [ ] Export a plain archive; import into a clean installation and compare every field and attachment. Repeat with a strong password. An incorrect password or changed encrypted payload must fail cleanly; an archive from another app must be rejected.
- [ ] Verify local storage fallback when signed out of iCloud. For cloud testing, use provisioned containers, inspect development schema, and test a second device on the same account. Export/import explicitly when transferring records between the separate local and cloud stores.
- [ ] Test Dynamic Type, VoiceOver, Reduce Transparency, Reduce Motion, dark mode, iPad split windows and live resizing. Background/reopen each window and check saved records persist.

## VaultGlass

- [ ] Import the synthetic Apex Electronics receipt as both image and PDF. Check merchant, $2,499 total, serial C02X9876Q6L4, the actual generated purchase date eleven months earlier, fourteen-day return window and twelve-month manufacturer warranty.
- [ ] Photograph/scan a real receipt and import a scanned image-only PDF. Check orientation, barcodes and multi-page scanning. Review and correct extracted details before relying on coverage estimates.
- [ ] Configure return and warranty dates in the future, grant notifications, and inspect pending alerts: return minus 48 hours and effective warranty minus 30 days. Check diagnostic checklist text. Denied permission must preserve the saved inventory item.
- [ ] Archive/return an item and verify pending reminders are canceled; restore it and refresh alerts.
- [ ] Drag inventory priorities. Filter Property and Room. Generate an insurance PDF with enough items for multiple pages; inspect photos, serials, purchase value and depreciated value.
- [ ] Enter an actual issue description and generate a claim draft. Check facts, attachments and escalation text. No claim is sent automatically.
- [ ] Ask Siri/Shortcuts for room warranty status and room value. Confirm archived items are excluded. Check detail entity annotations with AppIntentsTesting.
- [ ] Add the widget and verify summary refresh after scanning, archiving and restoring inventory.

## BioPulse Local

- [ ] Import the synthetic panel. Verify all eleven supported sample markers, including Vitamin D 24 ng/mL and ApoB 112 mg/dL.
- [ ] Check exact unit conversions: glucose mmol/L to mg/dL; creatinine µmol/L to mg/dL; cholesterol and triglyceride conversions; Vitamin D nmol/L to ng/mL; hs-CRP mg/L to mg/dL. Unknown units should fail with a clear review message.
- [ ] Verify the deterministic equation against the evaluation's independent calculation. A zero/nonpositive CRP or missing marker with no usable history must produce an incomplete estimate, not a fabricated number.
- [ ] Confirm historical substitutions use no future readings and are disclosed. The estimate is clamped to 18–110 per the supplied specification.
- [ ] Switch markers and HRV/resting-HR overlays. Check left/right axes, range shading, seven-day averages and intervention spans. Synthetic trends must be labeled.
- [ ] Request read-only HealthKit access; exercise authorized, denied and zero-sample cases. No health data is written. Verify sleep intervals from multiple sources are not double counted.
- [ ] Confirm educator summary, five physician questions and prominent medical disclaimer. Export and inspect a doctor brief PDF.
- [ ] Change the planned draw time, verify the twelve-hour countdown, daily hydration reset and supplement-review checklist. Guidance must defer to clinician/laboratory instructions.

## ClauseShield

- [ ] Select role and category, then import PDF, text and a camera scan. Open a PDF/text file from Files directly into the app.
- [ ] Audit the synthetic predatory contract. Check Net-90, pre-existing IP assignment, uncapped indemnity and non-compete flags. Missing protections should include late interest, termination/kill fee, liability cap and IP carve-out; the sample score should cap at 100.
- [ ] Test a protective freelance agreement and a residential lease with and without the four playbook protections. Negated mentions must not count as affirmative protection.
- [ ] Accept, dismiss and reset flags. Drag negotiation priority and relaunch to verify persistence. Accepted terms must appear in the negotiation draft.
- [ ] Import a revised version. Check additions/removals and exact matching of accepted replacement language in emerald. Review new-version risk rather than treating earlier flags as current facts.
- [ ] Change Collaborative, Commercial Standard and Firm / Walk-Away tones. Check all accepted counter-clauses and missing protection requests are included.
- [ ] Export a multi-page Redline Comparison Memo PDF and inspect original/replacement/rationale. Sharing opens the system share UI; the app does not email anyone automatically.

## Release gate

- [ ] Run an unsigned Release device build and a signed physical-device build for each app and widget.
- [ ] Exercise model-ready and fallback paths on physical hardware; measure memory for large image-only PDFs.
- [ ] Review clinical ranges and legal playbooks with qualified domain professionals before a public release.
- [ ] Configure App Store Connect products, privacy disclosure and support information, then test sandbox purchases separately from the local StoreKit catalog.
- [ ] Promote and validate CloudKit schemas before production distribution. Verify Debug QA overlays, overrides and launch seeding are absent in Release.

## Archive format compatibility

The unreleased QA archive format is now version 2. AES-GCM authenticates the app identifier as well as the payload. Version 1 development archives are intentionally rejected; re-export needed QA fixtures with the current build. No released customer migration is being claimed.

## Current release preparation

The three app IDs, three private iCloud containers and VaultGlass app group are registered and associated. Distribution provisioning, signed archives and production exports now pass package validation. This does not prove production CloudKit schema or device synchronization. App Store Connect records and metadata exist; see [submission status](../Submission/README.md).

SwiftUI scene restoration uses the framework's automatic restoration behavior and scene-stored tabs. Backgrounding must not manually call UIKit's restoration extension outside its permitted transition. Reproduce background/resume on hardware in each app and each supported window configuration.
