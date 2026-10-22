# Lightkeeper submission preparation

Prepared 2026-10-22. **Not ready to submit.** No physical-device recording or physical-device QA has been completed. No claim of App Review approval is made.

Public URLs:
- Marketing: https://fremxhk.github.io/lightkeeper.html
- Support: https://fremxhk.github.io/lightkeeper-support.html
- Privacy: https://fremxhk.github.io/lightkeeper-privacy.html
- Terms: https://fremxhk.github.io/lightkeeper-terms.html

Read `app-review-notes.md` for the six-point Guideline 2.1 draft, `recording-script.md` for device evidence, `physical-device-qa.md` for release gates, `services-and-privacy.md` for declarations, and `metadata.json` for proposed English metadata. These files contain no private review contact or API credentials.

The website is live: all four public HTML pages returned HTTP 200 on 2026-10-22. App Store Connect now contains **Lightkeeper: Lantern Puzzles**, app ID `6825834948`, bundle ID `app.lightkeeper.ios`, SKU `lightkeeper-ios`, English (U.S.), version 1.0. Apple rejected the short name as already used; the owner selected the descriptive store name. The in-app name remains Lightkeeper.

The listing text, Puzzle/Board game categories, privacy/support/marketing URLs, private review contact and six-point draft Notes are saved. Release is manual; status is Prepare for Submission. Nine offered IAPs have the exact USD reference prices; two subscriptions share the Keeper group and the same benefit level, with US prices and seven-day free trials. Three Game Center leaderboard records are created but not released. See `setup-status.json` for remote identifiers and remaining gates. Nothing has been submitted or uploaded.

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

`python3 Tools/inspect_app_store_connect.py` authenticates and reads matching app/bundle records only. It never uploads, mutates or submits. It uses Python 3, OpenSSL and a private JSON config at `~/.config/lightkeeper/app-store-connect.json` (override with `--config`). Config keys: `keyId`, `issuerId`, `privateKeyPath`; optional `reviewContact` stays private and is not printed. Set directory mode 700/file mode 600; keep the `.p8` outside git. The private contact has now been saved in App Review Information and verified by API read-back; it is deliberately absent from this public kit.

## Configuration details still requiring release validation

Subscription setup currently covers the US storefront only: $3.99 per month and $29.99 per year, both with a 7-day eligible trial. The API plan type is `UPFRONT`, meaning payment for each subscription period in full; it is not the new 12-month-commitment monthly-payment plan. Confirm release territories and configure the remaining local prices/trials before launch. The app itself has not been made available for sale. `starter_island` has not been created in ASC.

The daily leaderboard is configured with a 24-hour recurrence beginning 2026-10-23 00:00 UTC. The puzzle calendar uses local days; reconcile the competition's date/seed alignment before enabling it. Campaign and Duet boards are all-time, higher-is-better. Game Center resources still need release attachment and device validation.

The project now uses marketing version 1.0 and the verified developer team for all targets. Release simulator build passed (`/tmp/lightkeeper-asc-release-build.log`); this is not a signed device archive or physical-device QA. The current bank/tax/agreement status and EU trader declaration have not been attested or changed. No legal declarations were accepted on the owner's behalf.

The App Group is associated with the main app, widget and downloader; the iCloud container is associated with the main app. Live Activity declares no App Group entitlement. Capability associations were saved in Certificates, Identifiers & Profiles; production signing and two-device behavior remain unverified.

Age-rating answers are saved. Modern-OS global rating is 13+; legacy global rating is 12+, with regional exceptions. Leaderboard rankings are declared as frequent contests under [Apple's definitions](https://developer.apple.com/help/app-store-connect/reference/app-information/age-ratings-values-and-definitions). Duet has no broad distribution of arbitrary user content, no in-app messaging/chat or social feed; external sharing carries structured puzzle state. Revisit these answers before release if any functionality changes. No Kids Category age band is selected.

Validation: all 22 app tests passed after aligning StoreKit descriptions and equal-benefit subscription ranks (`/tmp/lightkeeper-asc-commerce-tests.log`). Remote read-back verified every USD price, both US trials, private review contact, manual release and draft state. No payment was made and no product/app was submitted.

The base app is configured as a free download (USD 0.00 base price, verified by API read-back). This does not release the app or complete territory selection. `app-store-connect-setup.jpg` is configuration evidence only; it is not an App Store gameplay screenshot or physical-device recording.
