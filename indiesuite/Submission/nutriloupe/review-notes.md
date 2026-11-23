# NutriLoupe — App Review information

Preparation for version 1.0.0. No developer registration or login is required.

1. **Demonstration:** No app account is required. Use the built-in synthetic example from the main capture or creation flow, then review the saved result and available exports. The example uses the same review screens as user-provided content.
2. **Purpose and audience:** Keep ingredient labels and a personal food-and-symptom journal with transparent association counts. Intended audience: Adults who want to organize food labels and their own meal and symptom observations. General-public distribution, not a private employee-only app.
3. **Access and setup:** Choose Scan an ingredient label, then Try a sample document. Open the saved food, review ingredient details and use Save journal entry. Open Explore 14-day symptom associations for the observed chart and denominators. Synthetic labels are generated locally; no health account or credentials are needed. Five completed AI actions are free; Pro enables additional actions. No external sample file or login credentials are required.
4. **External services:** Apple StoreKit/App Store for purchases; on-device health storage; SwiftData, PDFKit, Vision and Foundation Models for supported local data, OCR and generation. No developer-operated backend, third-party AI API, external tax/health/VIN/price data service, ad SDK or developer analytics endpoint is used.
5. **Regions:** English interface. The app and paid products are configured for USA availability for this submission. Apple determines purchase/trial eligibility and supported on-device model and speech language/region availability. System permissions depend on the user’s choices and platform. No separate regional service is supplied.
6. **Rights and regulated activity:** Educational organization only. This app does not diagnose conditions, certify allergens or food safety, or recommend treatment or an elimination diet. Ingredient-only processing classification is provisional. Symptom associations do not establish causation; consult a qualified clinician for health decisions. Users provide their own material; synthetic examples are generated locally. No regulated professional service, professional credential, certification or protected third-party content license is claimed. There are no app accounts or public user-content feeds.

Health records use an on-device SwiftData store, with no automatic CloudKit mirroring or iCloud/push entitlement. Health-data directories request exclusion from system backup. Complete health archives require a user-chosen passphrase; users explicitly choose any export destination.
## Evidence

Current consumer candidate: 1.0.0 (build 3), processed VALID and selected for this app version. The current suite passed 121 distinct target-qualified methods; repeated device/profile executions do not increase that count.

[Passing method inventory](../../Documentation/ConsumerTestInventory.md) · [Validation scope](../../Documentation/ConsumerValidation.md) · [Reviewed app flows](https://fremxhk.github.io/indiesuite/#flows) · [Signed build fingerprints](../../Documentation/BuildVerification.md).
