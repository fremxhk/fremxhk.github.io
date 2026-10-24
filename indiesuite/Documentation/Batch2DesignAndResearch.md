# Batch 2 design and implementation decisions

Status: implemented workflows are undergoing sequential testing. Compilation alone does not establish production readiness. Batch 1 App Review gates remain open.

## Interaction design

The five apps use native navigation, semantic system surfaces, readable hierarchy and explicit next actions. The primary screens pair a concise purpose statement with a single creation action and a persistent library. Generated results retain their source. Review precedes consequential actions: filing verification, native calendar/reminder dispatch, repair decisions and study grading. RecallGlass separates Study and Speak, so scheduling controls never compete with print-layout controls. Its PDF preview, export and AirPrint share one renderer. Large text uses scrolling rather than clipping on screen; overflowing print cards block export with an actionable message.

Apple's [printing guidance](https://developer.apple.com/design/human-interface-guidelines/printing) informed the native print sheet and disabled printing when unavailable. Native SwiftUI `onMove` and `swipeActions` implement reordering and decisions; the brief's `.reorderable()` and `.swipeActionsContainer()` spellings are not assumed to be SDK APIs.

## Scheduling and speech

RecallGlass implements the requested FSRS-5 forgetting curve, bounded stability/difficulty updates, same-day review handling and deterministic intervals without randomized fuzz. This is explicitly version 5, not a claim to implement newer FSRS versions. Reference: [FSRS algorithm](https://github.com/open-spaced-repetition/fsrs4anki/wiki/The-Algorithm) and the [version 5 scheduler](https://github.com/open-spaced-repetition/fsrs4anki/blob/v5.0.0/fsrs4anki_scheduler.js). Default parameters are fixed, not individually optimized. A learner confirms the final grade; an unavailable model falls back to a clearly identified conservative source/keyword comparison.

On-device transcription checks [supportsOnDeviceRecognition](https://developer.apple.com/documentation/speech/sfspeechrecognizer/supportsondevicerecognition) and requires it. Missing language support or permission produces an actionable error, never a server transcription fallback. Simulator audio uses synthetic transcripts. Meeting audio is temporary, protected with complete file protection, and removed when capture closes. RecallGlass also supports recording a spoken study answer before semantic review. Long-running recognition has a timeout and cancellation path.

## Tax-year and jurisdiction boundaries

The requested $0.70/mile is the **US 2025 business rate**, confirmed in [IRS Publication 463](https://www.irs.gov/publications/p463). For 2026, [Notice 2026-10](https://www.irs.gov/pub/irs-drop/n-26-10.pdf) specifies $0.725 for January–June and [Announcement 2026-11](https://www.irs.gov/irb/2026-29_irb) raises it to $0.76 from July. The UI records the tax year and the second-half mileage. Home-office and actual-cost comparisons are estimates that omit eligibility/income-limit/carryover decisions. A larger number is not an automatic deduction recommendation. User-supplied business purpose is evidence, not invented by an audit memo.

Singapore guidance is separately identified: [IRAS recordkeeping](https://www.iras.gov.sg/taxes/individual-income-tax/self-employed-and-partnerships/keeping-proper-records-and-accounts) generally requires five-year source records. US Schedule C calculations must not be presented as Singapore tax rules.

## Food classification and journal interpretation

The requested additive/oil/allergen penalties are an **unvalidated preference heuristic**, not a clinical nutrition score. [American Heart Association guidance](https://www.heart.org/en/healthy-living/healthy-eating/eat-smart/fats/healthy-cooking-oils) supports liquid plant oils as choices within a healthy diet; the UI does not imply seed oils are inherently harmful. The [FAO NOVA overview](https://www.fao.org/family-farming/detail/en/c/1735103/) and [UK SACN evidence update](https://www.gov.uk/government/publications/processed-foods-and-health-sacns-rapid-evidence-update/processed-foods-and-health-sacns-rapid-evidence-update-summary) inform the processing explanation and its limits. Ingredient-only processing classification is provisional. A limited token list cannot certify NOVA classification, food safety, allergens or cross-contact.

The 14-day chart reports Laplace-smoothed symptom-associated meal proportions, with denominators visible. Missing journal entries, repeated co-ingredients and the observation window limit interpretation. Associations do not establish causation. It is not a diagnosis or elimination-diet recommendation.

## Vehicle limitations

The VIN checker uses the 17-character transliteration/weight/check-digit method and discloses the repeating model-year cycle. [NHTSA guidance](https://www.nhtsa.gov/importing-vehicle/importation-and-certification-faqs-8) describes US VIN requirements. A passing checksum is not a vehicle-history, ownership or safety certification; check-digit requirements vary by market. No market-price benchmark is generated from a repair estimate. Benchmarks require an independently supplied source. Lease velocity uses miles driven since lease start and excludes taxes, fees, condition charges and market changes.

## QA and teardown

The root Swift Testing suite is serialized. The CLI uses a single iOS 27.0 iPhone destination, disables parallel execution and clones, runs the eight app schemes sequentially, rejects zero-test results, terminates apps and deletes only their disposable cache/tmp contents. It never clears other apps, system/model caches, stores or Keychain.

Swift does not permit suspension in `defer`; awaited cleanup is explicit in success and failure paths. In-memory SwiftData records are deleted while their contexts remain registered, autosave is disabled, PDF locals leave scope, and the shared model session/source context and URL cache are cleared. OCR images are scoped to a recognition call rather than retained in an engine buffer.

`peakMemoryDeltaMB` is the maximum resident-memory increase **observed by 20 ms sampling**, not a guaranteed allocation peak. MetricKit delivers delayed device-wide application reports and cannot truthfully supply an immediate per-test peak. The diagnostics disclose this distinction.

The existing repository uses `Scripts/`. On this case-insensitive macOS volume, the requested `scripts/run_sequential_simulator_qa.sh` resolves to that same directory; Git retains `Scripts/run_sequential_simulator_qa.sh` to avoid a case-colliding second directory.

A sequential run reproduced a SwiftData contract violation after erasing a store with deferred model notifications. Teardown now deletes records through its registered context, saves and processes pending changes, then releases context/container on return. It does not invalidate a store underneath live model objects.

## Physical screenshot review: clinician question grounding

A BioPulse build 4 screenshot exposed a gap in count-only assertions: five questions were present, but generated questions implied high WBC, low RDW and elevated ALP despite the synthetic values not supporting those premises. Build 5 source now composes neutral questions from verified canonical marker identities on every question/PDF surface, including archived panels. Unvalidated model question prose is not displayed. The hardware regression exercises misleading prompts, duplicate and unknown keys; installed build 5 verification remains a separate gate.

## Filled-field and deadline review

[Apple text-field guidance](https://developer.apple.com/design/human-interface-guidelines/text-fields) explains that placeholders disappear during editing. All five new apps now retain visible field labels, including units for numeric assumptions. Screenshot capture waits for navigation to settle. Visual review also caught an invented absolute date for a relative “Friday” commitment: EchoBrief now retains a model date only when its exact ISO date occurs in that task’s source quote; relative dates remain unset for owner verification. This is checked with explicit, relative and invalid calendar dates.

## Semantic-grading screenshot regression

A passing interaction run still exposed incorrect feedback: an answer identical to the displayed canonical answer received grade 1 because the model required an unrelated concept. Exact nonempty answers now bypass model grading, normalize whitespace/case and receive a correct/Good suggestion. Missing concepts are restricted to phrases present in that card’s canonical answer, with validation before accepting generated feedback. The learner still chooses the final FSRS grade. Academic unit and UI regressions explicitly verify the exact-answer case, including a distractor concept from another question.

The Singapore export path is also separate: it produces a business-record binder, omits US deduction shares and marginal-rate inputs, regenerates the memo for the selected framework, and states that stored USD amounts are not converted to SGD. Binders include only the selected tax year. The US path retains its Schedule C estimates.

## Cloud relationship structure

[Apple’s SwiftData sync guidance](https://developer.apple.com/documentation/swiftdata/syncing-model-data-across-a-persons-devices) requires optional relationships and explicit inverses where inference is not possible. The new study/cards, speech/cues, meeting/commitments, food/symptoms and repair/line-item relationships now include optional parent back-references and explicit inverses. Tests assert both sides after insertion/save. This structural check does not replace deployment of production schemas or two-device synchronization.
