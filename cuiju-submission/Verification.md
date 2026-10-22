# Submission preparation verification — 2026-10-22

This is a **prepared candidate**, not complete device coverage or App Review submission.

| Check | Result |
| --- | --- |
| App Store Connect API authentication | Passed with the user-supplied key; private key remains outside source/GitHub |
| App record | 6825805178, bundle com.hktwmahjong.app, version 1.0 in Prepare for Submission |
| Listing metadata | Traditional Chinese and English saved; field lengths checked |
| Review information | Six-part preparation notes and supplied review contact saved privately; physical evidence explicitly pending |
| Release mode | Manual |
| Game Center | Bundle capability, App Store provisioning profile and version setting enabled; real-device production testing pending |
| Pricing | Free price schedule prepared; Mac/Vision Pro compatibility distribution disabled |
| Privacy | App-specific URL saved; Data Not Collected answer saved as a draft, not published |
| Public documents | App-specific policy/support pages and submission drafts committed/pushed to GitHub; updated support email verified at public URLs |
| Icon | 1024×1024 RGB PNG; removed an unused alpha channel without changing the artwork |
| Signed device archive | Passed Release archive with distribution signing, Game Center entitlement, no debugging entitlement or inactive CloudKit entitlement |
| IPA export | Passed; current candidate is build/AppStore/ReadyExport/HKTaiwaneseMahjong.ipa |
| Local store preflight | Passed metadata limits, icon, free-release flags, packaged policy/font/license/privacy manifest, signatures, dSYM and public-page content checks |
| Apple package validation | VERIFY SUCCEEDED with no errors |
| App Store Connect candidate upload | UPLOAD SUCCEEDED with no errors; version 1.0 build 1; processing completed as VALID; usesNonExemptEncryption is false |
| Screenshots | Six primary-locale screenshots uploaded and all reported COMPLETE with no Apple delivery errors; iPhone and iPad captures are native pixels |
| Screenshot UI flow | Passed on both iPhone and iPad; iPad table captured in landscape |
| App integration tests | 11 passed, zero failures |
| Gameplay audit | Existing independent 100,000-hand scoring/settlement audit retained; no game-engine changes made during submission preparation |
| Physical iPhone QA | 11 integration + 8 gameplay UI tests passed; one initial trust-prompt interruption passed on targeted rerun |
| Release physical walkthrough | Passed normal unseeded hand through settlement/base/dealer/history on iPhone 18 Pro Max, iOS 27.2 RC 24B115; archived Release re-signed for development, code/resources matched |
| Requested review video | New 82.76-second physical TestFlight recording uploaded directly to App Review Attachment; Apple COMPLETE/errors[]; Notes updated; public backup verified HTTP 200 |
| Age rating | Saved: 18+ globally, R18+ Australia, 18+ Brazil; older OS 17+ with exceptions; Korea 19+ excluded |
| Storefronts | API and website verified: 145 enabled / 30 excluded (EU27, mainland China, South Korea, Vietnam); automatic new territories off |
| Content rights | Third-party font rights declared; bundled SIL OFL licence retained |
| TestFlight QA | Owner tester INSTALLED; 1.0 (1) selected for App Store version; 3/3 UI tests passed in-place, target installation unchanged |
| Review submission / release | Not performed |

Local evidence: `/private/tmp/cuiju-store-ready-archive.log`, `/private/tmp/cuiju-store-ready-export.log`, `/private/tmp/cuiju-apple-validation.log`, `/private/tmp/cuiju-store-integration-tests.log`, the screenshot capture logs, and `build/AppStore/` status/checksum records. Upload processing status is tracked separately from validation; do not interpret validation success as a TestFlight installation test.

Outstanding final declarations and distribution decisions are listed in README.md and Privacy-and-Rating.md. Replace the pending video/device entries in both the response and App Review Notes only after performing that work on the exact selected build.
