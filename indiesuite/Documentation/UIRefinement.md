# UI refinement — 23 October 2026

Direction: calm, polished utility with clear hierarchy. This is an implementation review and primary-source pattern study, not user-research statistics or proof of improved retention.

## Evidence and changes

| Observed issue in native captures | Consequence | Implemented refinement |
| --- | --- | --- |
| Receipt text-field labels disappeared when values were populated | Name, serial, location and amount could be confused | Persistent labels; receipt summary with currency and purchase date; separate receipt, coverage, location and optional settings sections |
| Dashboard explanatory and next-action cards preceded the core values | Extra reading and scrolling before understanding the record | Inventory valuation and PhenoAge lead their dashboards; contextual action cards are shorter; secondary explanations use disclosure |
| Lab controls, health status and setup text appeared ahead of the plot | The chart and its date axis did not fit in the initial viewport | Latest value, unit and date above a compact chart; 3M/6M/1Y/All period picker; comparison controls after the plot; visible legend and date axis |
| Long experiment labels clipped at the edge of the plot | Context became unreadable | Plot uses unobstructed interval marks; full intervention names and dates remain in the experiment section |
| Contract risk, missing protections, interpretation and instructions were all expanded | Too much reading before the first decision | Compact risk summary; expandable audit summary and omissions; All / To review / Saved filters |
| Raw `acceptedRedline` appeared in the UI and action labels wrapped | Implementation state leaked into the user flow | “Replacement saved to draft”; separate original and replacement treatments; short actions with a vertical accessibility fallback |
| Debug QA controls covered product content | Review screenshots were distracted by development controls | Screenshot launch mode hides the Debug overlay; ordinary Debug builds retain QA controls; Release excludes them |

## Primary-source pattern study

- [Apple Layout](https://developer.apple.com/design/human-interface-guidelines/layout): prioritize essential information and reveal secondary detail progressively. Applied to dashboard order, compact summaries and optional settings.
- [Apple Text Fields](https://developer.apple.com/design/human-interface-guidelines/text-fields): make the purpose of fields clear. Applied to persistent labels and explicit USD amount units.
- [NN/g: Placeholders in Form Fields Are Harmful](https://www.nngroup.com/articles/form-design-placeholders/): placeholder-only labels disappear and force people to remember field meaning. Applied directly to extracted receipts.
- [Apple Charts](https://developer.apple.com/design/human-interface-guidelines/charts): balance chart density, explanation and accessible alternatives. Applied to readable axes, legend, units and the saved-values disclosure.
- [Oura: Using Trends](https://support.ouraring.com/hc/articles/360055983614-Using-Trends): period selection and contextual tags provide ways to investigate a trend. Adapted as lab-history period selection and dated lifestyle experiments; no causal or efficacy claim is inferred.
- [Apple Health data guide](https://support.apple.com/en-euro/guide/iphone/iphe3d379c32/ios): summaries lead into category detail and graph exploration. Adapted to latest panel → selected biomarker → trend → source values.
- [Copilot Dashboard overview](https://help.copilot.money/en/articles/6045480-dashboard-tab-overview): a dashboard gives an overview of current state and upcoming items. Adapted to purchase valuation and real deadlines; no product-outcome comparison is claimed.
- [Juro AI Review](https://intercom.help/juro/en/articles/12691465-ai-review-in-juro): review uses a playbook and proposes changes for incorporation. Adapted to source-grounded quotes, role context and explicit review decisions; no professional legal capability is inferred.

## Validation and limits

Native captures were reviewed at the actual simulator resolution. The main UI/App Intents suite and final focused runs passed sequentially on the same iPhone 17e, including all three document workflows and chart/review/coverage capture paths. See TestResults.md for exact per-bundle scopes and counts. No concurrent simulator destinations or clones were used. The core numerical and persistence suite is recorded separately in Validation.md.

No usability participants were recruited and no retention, conversion or task-time improvement has been measured. Physical-device accessibility, iPad layouts and the exact signed App Store build still require QA. The candidate is prepared for further review, not certified App Store-ready.

The latest captures are in [Previews/Refined](Previews/Refined). Earlier captures are retained as a comparison baseline.

## Contrast refinement

A final screenshot review identified bright teal/green/orange text on light cards. These accents now use darker light-mode values and brighter dark-mode values; status labels retain icons and explicit text. The target is at least 4.5:1 for ordinary text, following [W3C contrast guidance](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html). This is a palette improvement, not a claim that every screen has completed a full accessibility certification.

The automated main-screen audit identified the system blue Pro label on VaultGlass's glass control as a contrast failure. VaultGlass now uses a darker light-mode blue; all adaptive text accents, including secondary text, are tested against light/dark card and badge surfaces. The visible-content audit passed after strengthening secondary captions and native section headers. Native toolbar and viewport exceptions are explicitly described in the validation report.

## Final accessibility layout review

The largest-text screenshots revealed an overlap that tap/existence tests did not detect in BioPulse's native marker picker. The chart now uses an explicit menu label, stacks its selector/reading/date at accessibility sizes, reduces axis density and preserves scaled caption labels. A layout assertion verifies the selector ends above the reading, and the UI workflow changes to Albumin and back to Fasting Glucose. The accessibility-size PhenoAge card uses a text summary instead of squeezing large labels into a fixed ring. Receipt amounts remain an atomic line with a spoken currency value. Chart legends identify the lab reference band and intervention span as well as the primary measurement and optimal interval.

These changes passed normal and dark/accessibility XXXL UI runs and were reviewed in native captures. Passing control interactions alone is not treated as evidence that the rendered layout is correct.

## iPad capture findings

The 13-inch iPad capture revealed a selected-sidebar contrast issue: a red risk badge appeared directly over the indigo selected row. The badge now has an opaque semantic backing so selection cannot change its contrast. VaultGlass’s two secondary valuations now expose separate explicit spoken labels/values rather than relying on automatic grouping. BioPulse’s experiment setup uses a menu of named markers instead of requiring internal biomarker codes; saved experiments display marker names. The final focused regression checks menu selection and the affected receipt, contract and accessibility flows.

## Paid-state review on physical hardware

Physical TestFlight captures showed that an already active Pro user was still offered a new subscription. The shared access screen now shows a compact access summary, identifies lifetime ownership, and presents subscription management only for an existing subscriber. Purchase options wait for access resolution and are hidden while Pro is active; an additional manager-level guard prevents another purchase. The management action uses [Apple’s native subscription sheet](https://developer.apple.com/documentation/StoreKit/AppStore/showManageSubscriptions(in:)), with account-settings guidance on unsupported iOS-on-Mac hosts. Local StoreKit regression coverage verifies lifetime ownership, duplicate-purchase suppression and active subscription states across the eight app namespaces.


## Warranty assessment letter completeness

Reviewing the real build 3 claim screen found an incomplete letter and empty attachments section. Build 4 validates generated text against the saved receipt facts and the reported issue, supplies a source-based letter when necessary, and always provides a consistent proof-of-purchase, product/serial photo and issue photo/video checklist. Unknown identifiers remain explicitly unrecorded. Three focused core regressions and the fresh-receipt-to-letter simulator UI flow passed. Native simulator captures were visually reviewed for complete source facts, the three evidence requests and the share control. The revised physical screen and final video remain pending.
