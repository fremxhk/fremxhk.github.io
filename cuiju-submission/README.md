# 翠局 1.0 — App Store submission package

Prepared 2026-10-22. **Draft preparation; not submitted for review.** Physical-device QA and Apple's requested video remain pending.

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
- `Review-Notes.txt`: under 4,000 characters, staged as preparation notes; explicitly identifies pending physical QA/video.
- `Guideline-2.1-Response-DRAFT.txt`: full six-part response draft. Do not send before completing evidence.
- `Physical-Device-QA.md`: recording shot list, physical testing checklist and evidence record.
- `Privacy-and-Rating.md`: source-based privacy, age-rating, encryption and regional worksheet. Final questionnaire declarations remain pending.
- `LXGW-OFL.txt`: third-party font copyright/license; also bundled in the app.
- `ExportOptions.template.plist`: export template. Never place API private keys in this directory or commit them.
- `Screenshots/`: local iPhone 6.9-inch and iPad 13-inch native simulator captures; `capture.log` records the UI tests. These are listing assets, not the physical-device recording Apple requested.

## Preparation completed

The app has an offline-readable privacy policy and links to its public policy/support pages. Free-release settings no longer advertise the removed hint feature or show Restore Purchases. The base build has no Google SDK, AdMob identifier or tracking permission text. The optional ads project retains its separate plist and is not the submission target. Unconfigured private party-code UI is hidden.

Cloud saves are disabled and the free build requests only Game Center entitlement; `CloudEnabled.entitlements` is retained solely as an opt-in template. If cloud saving is enabled later, restore its account capabilities, deploy the schema, test migration and update privacy disclosures. Do not copy it into the current candidate.

App Store Connect integration uses the locally supplied API key, with tokens generated in memory and no private-key contents stored in source, GitHub or logs. The matching distribution certificate is installed. The explicit bundle ID, Game Center capability and App Store provisioning profile were prepared through Apple's API. The app record was created on Apple's website.

## Required before review submission

- [ ] Complete the physical iPhone/iPad testing and latest-public-OS device recording in `Physical-Device-QA.md`.
- [ ] Attach the recording, identify exact device/OS/build/date, finish the six-part response, and replace the pending note in App Review Information. Simulator assets do not satisfy this request.
- [ ] Provide the review contact telephone number. Support email is already known; do not invent a phone number.
- [ ] Confirm privacy questionnaire and rating answers against the final binary and actual practices. The conservative simulated-gambling recommendation and regional implications are explained in `Privacy-and-Rating.md`.
- [ ] Choose storefronts and satisfy any regional game classification/publication requirements. EU availability also needs the account holder's trader-status declaration/verification.
- [ ] Set the free price schedule, confirm agreements/account requirements and assess Apple's current accessibility declaration questions. Do not claim unverified accessibility support.
- [ ] Upload the tested candidate to TestFlight, verify processing/export compliance, enable and test production Game Center, and select the final build for the version.
- [ ] Recheck final screenshot set, including landscape iPad captures; use real gameplay prominently. Screenshots must accurately match the selected binary. Do not use the earlier portrait iPad table capture if superseded.
- [ ] Run final Apple validation and review the complete staged metadata. Keep release manual until launch is deliberately approved.

## Local commands

From the application project directory:

```sh
python3 Scripts/appstore-connect.py inspect
python3 Scripts/stage-store-metadata.py
python3 Scripts/store-preflight.py --archive build/AppStore/Cuiju-1.0-final.xcarchive --online
```

The first two commands require the private local configuration in `~/.config/cuiju-appstore/config.json`; it references the API key in Downloads. The scripts do not submit to review or release the app. `archive-appstore.sh` accepts `CUIJU_TEAM_ID`, `CUIJU_PROFILE_NAME` and optional archive/export paths. It archives, checks the signed bundle and exports a local IPA. `capture-store-screenshots.py <simulator-udid> iphone|ipad` captures native pixels from an opt-in UI test.

Gameplay logic already has a separate 100,000-hand audit stored with the application project. That audit verifies scoring/ledger behavior and does not replace device or production multiplayer testing.

## Apple references

[Submission requirements](https://developer.apple.com/app-store/submitting/), [Review guidelines](https://developer.apple.com/app-store/review/guidelines/), [privacy definitions](https://developer.apple.com/app-store/app-privacy-details/), [rating definitions](https://developer.apple.com/help/app-store-connect/reference/app-information/age-ratings-values-and-definitions/) and [screenshot specifications](https://developer.apple.com/help/app-store-connect/reference/app-information/screenshot-specifications).
