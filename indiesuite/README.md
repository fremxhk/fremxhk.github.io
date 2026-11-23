# IndieSuite

A local Xcode 27 workspace with VaultGlass, BioPulse Local, ClauseShield, DeductGlass, EchoBrief, NutriLoupe, TorqueShield, dual-mode RecallGlass, a VaultGlass WidgetKit extension, and six shared IndieCoreKit library products. Minimum OS: iOS/iPadOS 27.0. Built with the installed Swift 6.4 toolchain and complete concurrency checking.

Open `IndieSuite.xcworkspace` and choose an app scheme. Each app starts with an empty private database; the Debug QA badge can seed six historical records or run a generated document through the live OCR/model pipeline. An unavailable or failing system model uses deterministic local extraction, and the telemetry sheet reports which route ran.

## Layout

- `Config`: shared build settings and the 24-product StoreKit catalog.
- `Packages/IndieCoreKit`: design, StoreKit/Keychain, Vision/FoundationModels, SwiftData/CloudKit/archives/PDF, and QA infrastructure.
- `Apps`: eight apps and a widget. Batch 1 retains its source layout. Shared, testable Batch 2 models, schemas and calculations live in IndieCoreStudios; each app owns its UI and platform interactions.
- `Tests/IndieSuiteEvaluationsTests`: serialized Swift Testing evaluations, exact numerical checks, OCR fallback, archive integrity, StoreKit, and typed intent execution.
- `Tests/IndieSuiteUITests`: sequential app launch, demo seeding, live synthetic document workflows and AppIntentsTesting against each running app.
- `Documentation/OnDeviceQA.md`: signing, physical-device verification and feature walkthrough.
- `Documentation/Validation.md`: automated results, device builds and hardware QA limits.
- `Documentation/UIResearch.md`: cited UI research, app-specific return-use hypotheses and implemented design decisions.
- `Scripts/test-sequential.sh`: builds with two jobs and tests on one caller-selected simulator, without parallel destinations or test clones.

## Build and test

The generated Xcode project is included; XcodeGen is needed only when changing the project manifest. `xcodegen generate` regenerates it from `project.yml`.

```sh
xcodebuild -workspace IndieSuite.xcworkspace -scheme VaultGlass \
  -destination 'generic/platform=iOS' CODE_SIGNING_ALLOWED=NO build

# Choose one existing, booted simulator. All app tests reuse this same UDID.
Scripts/test-sequential.sh YOUR_SIMULATOR_UDID
```

[Production readiness](Documentation/ProductionReadiness.md) lists unresolved release gates; [test results](Documentation/TestResults.md) enumerate completed checks.

The eight app schemes reference `Config/IndieSuiteProducts.storekit`. The catalog and all 24 saved US App Store prices specify $0.99 monthly, $5.99 annual with an eligible one-week introductory trial, and $14.99 lifetime per app. Availability is USA-only and release is manual. Live App Store pricing and eligibility are supplied by StoreKit. Local StoreKit configurations apply to Xcode-launched Debug runs; release/TestFlight purchases require matching products in App Store Connect.

## Batch 2

RecallGlass separates academic active recall from corporate speaking. Its print renderer imposes 3×5, 4×6 and A6 cutouts on A4 or Letter at 72 points/inch, retains exact source evidence, retimes reordered cards, previews the exported PDF and supports stage rehearsal and AirPrint. Oversized card text blocks export instead of clipping.

DeductGlass keeps receipt/CSV evidence and tax-year-specific US method comparisons. EchoBrief links commitments to transcript quotes, captures audio on device and requires verification before Reminders/Calendar dispatch. NutriLoupe explains its provisional processing classification and unvalidated preference score, with noncausal 14-day journal associations. TorqueShield validates VIN check digits and keeps independently sourced market benchmarks separate from quoted repair prices.

See [research and implementation decisions](Documentation/Batch2DesignAndResearch.md). Current consumer features passed their documented validation; see ProductionReadiness.md for distribution scope and the unsubmitted review drafts.

```sh
Scripts/run_sequential_simulator_qa.sh YOUR_IOS_27_0_SIMULATOR_UDID
```

The nine serialized app/mode cases use one simulator and explicit awaited cleanup. The floating Debug QA panel can also run the nine subsystem smoke checks sequentially. Sampled resident-memory increases are distinguished from delayed MetricKit reports.

## Data and interpretation

OCR, generation, document rendering, risk scoring and lab calculations run locally. No third-party key or server is required. FoundationModels profiles change instructions, temperature and document evidence tools within the same model session. Source documents are untrusted data. Contract flags require a source quote, and deterministic checks supplement model extraction.

VaultGlass, ClauseShield, DeductGlass, EchoBrief, TorqueShield and RecallGlass use a private CloudKit configuration with a durable SQLite cache. Account unavailability retains the same cache URL; if cloud-container initialization fails, local fallback opens that same file. A legacy Local store is adopted when no Cloud cache already exists. Earlier separate stores are preserved and are not automatically merged; keep a portable archive before account/storage changes and contact Support if earlier records are not visible. App windows and intents share one container. BioPulse Local and NutriLoupe use on-device health storage with complete file protection; see [health storage and recovery](Documentation/HealthStoragePolicy.md).

All eight apps provide portable archives preserving stored domain fields, binary attachments and child relationships. Both health apps require password-protected archives and a passphrase of at least 12 characters. The other six apps offer a plain archive or optional password protection. Protected archives use AES-GCM and PBKDF2-HMAC-SHA256 with a random 32-byte salt and 210,000 iterations. Passwords are not retained. Import merges new identifiers and preserves existing identifiers.

Free usage is reconciled between Keychain and UserDefaults; quota storage errors fail closed. This is local tamper resistance, not a guarantee against a compromised device. Debug entitlement overrides do not ship in Release.

PhenoAge implements the equation supplied in the request, with stable logarithmic evaluation and an 18–110 clamp. Missing core markers may use the latest historical value at or before the panel date. Reused markers are disclosed. Lab reference and optimal intervals are explicitly illustrative reference intervals, not individualized clinical thresholds. HealthKit demo data is visibly labeled synthetic. Neither lab summaries nor contract screening replace professional review.

## SDK decisions

The installed SDK's entity annotation API is `.appEntityIdentifier(EntityIdentifier(for: ...))`. It is used on the inventory detail screen. SwiftUI scenes use `.restorationBehavior(.automatic)` with scene-stored selected tabs; manually extending UIKit restoration during backgrounding is invalid and was removed after a reproduced crash. `MXMetricManager` supplies MetricKit payloads; live inference elapsed time and resident memory are measured separately. Apple's system-owned PDF/text UTIs are imported rather than incorrectly re-exported as app-owned types. A receipt with no reliable total or purchase date is rejected instead of silently assigning invented values. Unknown biomarker units are rejected before numerical calculations.

The revised consumer candidates passed their current 121-method validation and signed-package checks, and remain in unsubmitted App Review drafts with automatic release after approval. ClauseShield is a 1.0.1 update to its existing live 1.0.0; the other seven candidates use 1.0.0. Follow [current validation](Documentation/ConsumerValidation.md) and [production readiness](Documentation/ProductionReadiness.md) for evidence and the final distribution scope. Production service checks and five-process SDK synchronization lifecycles passed for all six cloud-enabled apps; [the evidence inventory](Documentation/ProductionMirroringResults.md) distinguishes these signed Mac Catalyst client checks from iOS distribution execution.
