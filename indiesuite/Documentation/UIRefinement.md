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

Native captures were reviewed at the actual simulator resolution. All nine updated live Siri/UI checks passed sequentially on the same iPhone 17e, including all three document workflows and additional chart/review/coverage capture paths. No concurrent simulator destinations or clones were used. The core numerical and persistence suite is recorded separately in Validation.md.

No usability participants were recruited and no retention, conversion or task-time improvement has been measured. Physical-device accessibility, iPad layouts and the exact signed App Store build still require QA. The candidate is prepared for further review, not certified App Store-ready.

The latest captures are in [Previews/Refined](Previews/Refined). Earlier captures are retained as a comparison baseline.
