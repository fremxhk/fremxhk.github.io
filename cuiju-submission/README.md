# 翠局 1.0 — App Store submission package

**Submitted for App Review on 2026-10-23 at 01:13 HKT. Version 1.0 (1): Waiting for Review. Automatic release after approval is enabled.**

## Product and public documents

| Field | Prepared value |
| --- | --- |
| App | 翠局・港式台牌 / Cuiju: Hong Kong Mahjong |
| App Store Connect ID | 6825805178 |
| Bundle ID | com.hktwmahjong.app |
| Version / build | 1.0 / 1 |
| Minimum OS | iOS / iPadOS 18.0 |
| Supported devices | iPhone and iPad |
| Launch business model | Free, no ads, no enabled in-app purchases |
| Primary listing language | Traditional Chinese; English listing also prepared |
| In-app language | Traditional Chinese |
| Support email | chkchkchkc@gmail.com |
| Privacy policy | https://fremxhk.github.io/cuiju-privacy.html |
| Support / marketing URL | https://fremxhk.github.io/cuiju-support.html |
| Draft listing | https://appstoreconnect.apple.com/apps/6825805178/distribution |

App-specific policy and support pages are in the developer's [GitHub Pages repository](https://github.com/fremxhk/fremxhk.github.io). Submission documents are mirrored under `cuiju-submission/` there. Use the app-specific policy rather than the portal's generic advertising policy.

## Contents

- `metadata.json` and `Metadata/`: copy-ready Traditional Chinese and English listing fields, with length checks.
- `Verification.md`: completed preparation checks and the limits of that evidence.
- `Review-Notes.txt`: final six-part notes, saved and included in the review submission.
- `Guideline-2.1-Response.txt`: submitted six-part response; the older DRAFT file is historical.
- `Physical-Device-QA.md`: recording shot list, physical testing checklist and evidence record.
- `Privacy-and-Rating.md`: source-based privacy, age-rating, encryption and regional worksheet. Age/content/storefront declarations saved; privacy declaration published.
- `LXGW-OFL.txt`: third-party font copyright/license; also bundled in the app.
- `ExportOptions.template.plist`: export template. Never place API private keys in this directory or commit them.
- `Screenshots/`: local iPhone 6.9-inch and iPad 13-inch native simulator captures; `capture.log` records the UI tests. These are listing assets, not the physical-device recording Apple requested.

## Preparation completed

The app has an offline-readable privacy policy and links to its public policy/support pages. Free-release settings no longer advertise the removed hint feature or show Restore Purchases. The base build has no Google SDK, AdMob identifier or tracking permission text. The optional ads project retains its separate plist and is not the submission target. Unconfigured private party-code UI is hidden.

Cloud saves are disabled and the free build requests only Game Center entitlement; `CloudEnabled.entitlements` is retained solely as an opt-in template. If cloud saving is enabled later, restore its account capabilities, deploy the schema, test migration and update privacy disclosures. Do not copy it into the current candidate.

App Store Connect integration uses the locally supplied API key, with tokens generated in memory and no private-key contents stored in source, GitHub or logs. The matching distribution certificate is installed. The corrected signed archive and exported IPA are stored locally under `build/AppStore/Cuiju-1.0-ready.xcarchive` and `build/AppStore/ReadyExport/`. The app icon is fully opaque with no alpha channel. The explicit bundle ID, Game Center capability and App Store provisioning profile were prepared through Apple's API. The app record was created on Apple's website.

## Submission record

Version 1.0 (1) has been accepted into Apple's review queue. The published privacy declaration is Data Not Collected. The final six-part response and clean physical TestFlight video are included in App Review Information; Apple processed the direct video attachment as COMPLETE without errors. The release setting is **Automatically release this version**.

`Submission-Status.json` records the submission ID, timestamp and release setting. `Guideline-2.1-Response.txt` is the final response. Earlier DRAFT files and dated QA entries are historical preparation records and do not describe the current submission status. The submitted physical-device evidence reports the three completed TestFlight tests; it does not claim additional testing.

## Local commands

From the application project directory:

```sh
python3 Scripts/appstore-connect.py inspect
python3 Scripts/stage-store-metadata.py
python3 Scripts/store-preflight.py --archive build/AppStore/Cuiju-1.0-ready.xcarchive --online
```

The first two commands require the private local configuration in `~/.config/cuiju-appstore/config.json`; it references the API key in Downloads. The scripts do not submit to review or release the app. `archive-appstore.sh` accepts `CUIJU_TEAM_ID`, `CUIJU_PROFILE_NAME` and optional archive/export paths. It archives, checks the signed bundle and exports a local IPA. `capture-store-screenshots.py <simulator-udid> iphone|ipad` captures native pixels from an opt-in UI test.

Gameplay logic already has a separate [100,000-hand audit](../Audit/updated-rules-100000/Report.md). That audit verifies scoring/ledger behavior and does not replace device or production multiplayer testing.

## Apple references

[Submission requirements](https://developer.apple.com/app-store/submitting/), [Review guidelines](https://developer.apple.com/app-store/review/guidelines/), [privacy definitions](https://developer.apple.com/app-store/app-privacy-details/), [rating definitions](https://developer.apple.com/help/app-store-connect/reference/app-information/age-ratings-values-and-definitions/) and [screenshot specifications](https://developer.apple.com/help/app-store-connect/reference/app-information/screenshot-specifications).
