# IndieSuite submission preparation

Prepared metadata and review evidence for VaultGlass, BioPulse Local and ClauseShield. Submission is deliberately pending physical-device QA and video evidence requested under Guideline 2.1.

## Completed preparation

- Forty-five distinct target-qualified automated test methods passed in the recorded scopes. [Every method, pass result and supporting bundle](../Documentation/TestResults.md) is listed; repeat executions are separate. Functional tests reused one iPhone 17e sequentially. Final affected flows passed four normal and four dark/accessibility XXXL tests.
- Three final signed Release archives and App Store production exports passed deep/strict signature, bundle/version/build, entitlement, privacy-resource and Debug-flag exclusion checks. [Package fingerprints and exact scope](../Documentation/BuildVerification.md) are recorded.
- Final builds uploaded, processed as VALID and were selected for version 1.0.0: VaultGlass build 2, BioPulse Local build 3, ClauseShield build 2. Per-build TestFlight QA instructions are saved; automatic tester notifications are disabled. An explicitly authorized internal tester has been invited to an internal-only QA group for each final build. Invitation acceptance and on-phone TestFlight installation remain pending. No beta review submission, App Review submission or public release occurred.
- Three English metadata sets: app name, subtitle, description, keywords, promotional text, copyright, category, version, SKU, privacy/support/marketing URLs. Private App Review contacts and six-point review notes are saved without publishing private contact details to GitHub.
- Nine products matching the app catalog: monthly $4.99 USD, annual $29.99 USD with a one-week eligible USA introductory trial, lifetime $79.99 USD. Individual App Store purchase options are configured. Product availability remains USA only pending final rollout confirmation.
- Nine IAP review screenshots and eleven genuine current-size App Store screenshots processed successfully. The screenshot slots cover 1206 × 2622 iPhone and 2064 × 2752 iPad captures, without resizing. They show the app in use with demonstration data and are not physical-device certification.
- Three app bundle IDs and widget ID registered. Three private CloudKit containers and the VaultGlass App Group are registered/associated. Production schema and two-device runtime verification remain open.
- Public support/privacy pages and in-app policy links are present. Three Data Not Collected privacy drafts and age questionnaires are saved; privacy publication remains pending Apple's legal attestation.
- Three unsubmitted review drafts exist. All nine products and all three subscription groups are attached to unsubmitted drafts. Apple-converted UPFRONT prices are saved for all 175 pricing territories; this does not widen product availability beyond USA. Draft creation is not submission for review.

## App Store Connect records created

| App | App ID | Bundle ID |
| --- | --- | --- |
| VaultGlass | 6826259569 | com.indiesuite.vaultglass |
| BioPulse Local | 6826259946 | com.indiesuite.biopulselocal |
| ClauseShield | 6826260497 | com.indiesuite.clauseshield |

Version 1.0.0, English (U.S.), manual release. Names, subtitles, descriptions, keywords, promotional text, public URLs, copyright, categories and review notes/contact are saved. Base apps are free. Nine products and their localizations, three subscription groups, USD prices and annual introductory offers are saved. Age questionnaires are saved; BioPulse and ClauseShield use an adult override. These are setup records, not submitted/reviewed products.

All three Data Not Collected privacy drafts are saved. Publishing displays Apple's legal accuracy/compliance attestation and remains pending explicit confirmation. Review notes clearly state that physical-device evidence is pending. No response falsely claiming hardware QA has been sent.

## Apple’s final draft validation

Apple accepts the selected builds and current screenshot slots. Adding each app version to its unsubmitted draft currently returns exactly two declaration blockers:

- `contentRightsDeclaration` is required.
- App Privacy answers must be published.

These are left for explicit owner confirmation. The drafts are not submitted, and hardware/live-service/domain gates still apply even after the metadata blockers are resolved.

## Privacy and age-rating worksheet

- No tracking, ads, developer-operated accounts, public user-content feeds or third-party AI/analytics SDKs.
- Document recognition and generation operate on device. CloudKit uses each user’s private container; raw HealthKit samples are read locally and not persisted into CloudKit or archives.
- Proposed privacy answer is Data Not Collected, contingent on confirming the final signed build and any optional Apple diagnostic-report handling. Apple [defines collection](https://developer.apple.com/app-store/app-privacy-details/) in terms of off-device access by the developer/partners; on-device-only processing is not collection. Do not infer that privacy manifests replace the App Store questionnaire.
- All apps: no chat, public UGC, ads, gambling, purchases of physical goods, mature entertainment, violence or unrestricted web browsing. In-app purchase access exists.
- BioPulse: health/medical information is present. Complete the current health/wellness and medical-treatment-information questions accurately; the intended audience is adults. Do not assert regulatory clearance. Confirm the Regulated Medical Device declaration with the developer before submitting.
- ClauseShield: legal screening/drafting, no legal representation or jurisdiction-specific enforceability guarantee.
- No protected third-party library of content is bundled. Synthetic samples are generated by the app; users supply their own documents.
- Encryption uses platform CryptoKit/CommonCrypto for archive protection, without a custom cryptographic algorithm. The binary currently declares no non-exempt encryption; validate the current export-compliance questionnaire and territories before submission.

## Remaining release gates and owner input — last

1. Complete physical iPhone and iPad QA on the exact signed Release/TestFlight builds, including camera/OCR, model-ready/fallback behavior, permissions, large documents/memory, notifications/widget, VoiceOver/largest text, offline use and data retention. Follow [the unchecked hardware walkthrough](../Documentation/OnDeviceQA.md). The iPhone has reconnected. Physical XCTest is awaiting the owner-completed iOS passcode prompt to enable UI automation; no hardware test is counted as passed yet.
2. Verify live App Store sandbox/TestFlight purchases, trial eligibility, renewals/cancellation, refunds/revocation, pending/failed purchases and restore. Local StoreKit test passes do not certify Apple's live service.
3. Validate/deploy the CloudKit production schema after signed hardware testing and confirm synchronization on two devices, signed-out fallback and explicit local/cloud transfer behavior.
4. Obtain qualified review of the illustrative health calculations/ranges and legal screening/playbooks. No clinical validation, medical-device clearance or jurisdiction-wide legal guarantee is claimed.
5. Confirm final rollout territories and owner declarations: privacy publication, content rights, BioPulse regulatory status, encryption/export classification and any applicable trader/account agreements/tax/banking information. Proposed encryption classification is exempt platform-based protection; owner confirmation remains a submission gate.
6. Finish the unsubmitted review package after those confirmations, append the real device/OS/build/video URL to the Notes field and send Apple's Guideline 2.1 response only after the physical launch-to-flow recording exists. Demonstrate paid access/restore in the recording. No simulator video may substitute.

Apple's privacy Publish dialog states that publishing agrees to accuracy, App Store guidelines and applicable law; explicit confirmation is required for that action. All three drafts remain unpublished until confirmed. No response claiming hardware QA or production readiness has been sent.
