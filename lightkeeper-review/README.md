# Lightkeeper submission preparation

Prepared 2026-10-22. **Not ready to submit.** No physical-device recording or physical-device QA has been completed. No claim of App Review approval is made.

Public URLs:
- Marketing: https://fremxhk.github.io/lightkeeper.html
- Support: https://fremxhk.github.io/lightkeeper-support.html
- Privacy: https://fremxhk.github.io/lightkeeper-privacy.html
- Terms: https://fremxhk.github.io/lightkeeper-terms.html

Read `app-review-notes.md` for the six-point Guideline 2.1 draft, `recording-script.md` for device evidence, `physical-device-qa.md` for release gates, `services-and-privacy.md` for declarations, and `metadata.json` for proposed English metadata. These files contain no private review contact or API credentials.

The API key was authenticated successfully on 2026-10-22. The account had no matching Lightkeeper app record or `app.lightkeeper.ios` bundle identifier. Apple requires creation of the initial app record on the App Store Connect website. No app was submitted and no App Review message was sent. Recheck account state before configuration.

## Account configuration order
1. Register the app and extension identifiers with the capabilities actually required by each target. App: `app.lightkeeper.ios`; extensions: `.widget`, `.liveactivity`, `.assets`. Configure App Group `group.app.lightkeeper.ios` and iCloud container `iCloud.app.lightkeeper.ios`; reconcile provisioning against project entitlements.
2. Create the iOS app record: name Lightkeeper (subject to availability), primary language English (U.S.), bundle ID `app.lightkeeper.ios`, SKU `lightkeeper-ios`. Configure the real development team locally. Do not alter unrelated app records.
3. Complete paid agreements, banking/tax details, age-rating questionnaire and App Privacy responses using the signed archive and actual service behavior. Do not select "Data Not Collected" solely because the app has no custom server.
4. Configure visible products from `products.json`, localized descriptions/prices and review screenshots. Keep `starter_island` unavailable until its benefit is defined. Configure subscription group and eligible 7-day introductory offer. Submit relevant IAPs with the first app version.
5. Configure Game Center leaderboards `beacon.daily`, `campaign.stars`, `duet.wins`; upload and validate all nine additional-island packs. Confirm whether the app's GameSave entitlement/container requirements match the production team.
6. Refresh season dates/content for actual launch. The current season starts 2026-10-19 and runs 28 days; do not sell an ended season as current.
7. Archive, validate, upload to TestFlight and complete every physical-device and deployment-target gate. Add actual screenshots showing gameplay, not only artwork or launch screens.
8. Fill private review contact in App Store Connect (supplied separately), attach build, recording URL and all six review answers. Only then send the response and submit, with owner authorization.

Apple references: [App records API limitations](https://developer.apple.com/documentation/appstoreconnectapi/apps), [App completeness](https://developer.apple.com/app-store/review/guidelines/#app-completeness), [IAP configuration](https://developer.apple.com/help/app-store-connect/configure-in-app-purchase-settings/overview-for-configuring-in-app-purchases/).

## API integration

`python3 Tools/inspect_app_store_connect.py` authenticates and reads matching app/bundle records only. It never uploads, mutates or submits. It uses Python 3, OpenSSL and a private JSON config at `~/.config/lightkeeper/app-store-connect.json` (override with `--config`). Config keys: `keyId`, `issuerId`, `privateKeyPath`; optional `reviewContact` stays private and is not printed. Set directory mode 700/file mode 600; keep the `.p8` outside git. The configured local private contact still needs to be entered into the actual App Review Information fields once the app exists.
