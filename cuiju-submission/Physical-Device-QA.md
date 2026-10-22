# Physical-device QA and Guideline 2.1 recording

Status: **physical iPhone automation completed; clean offline review video prepared; remaining device/TestFlight coverage pending**. Simulator UI captures and the 100,000-hand engine audit are supporting evidence only. Do not submit for review with pending evidence or paste the unfinished response as if testing had occurred.

## Record the exact candidate

Install the signed candidate using TestFlight when available. Record version/build, device model, exact OS version/build (record RC status when applicable), date, and whether it is the same build selected in App Store Connect. Re-test after any binary change. Test at least physical iPhone and iPad because both platforms are supported; use the latest public OS for the requested video, and cover minimum-supported OS and a small iPhone as device access permits.

## Video shot list

1. Begin with a genuine cold launch/loading screen on a physical device and show the lobby. Exclude private Home Screen content and personal system overlays.
2. Open single-player, show landscape layout, normal draw/discard, retained-draw automatic sorting, legal claims and pass. Play through a hand and show the full score receipt including base and dealer components; record longer if needed instead of fabricating a win.
3. Show exposed melds/flowers, chronological center discards, history and custom rules. Enable exchange and demonstrate one die roll, exact player selection and received tiles in a game that reaches an exchange phase.
4. Show table themes, offline privacy policy and public support link. Demonstrate that this build has no purchase or advertising flow.
5. With a second physical device, show nearby connection/permission, then Game Center login/match/invitation if online multiplayer is offered. Record normal play on both sides, interruption/reconnection, and bot substitution. Do not share Apple account credentials or expose private notifications in the video.
6. There is no developer account registration/deletion, content posting/chat or paid-content flow to demonstrate. State this in the response; do not create a misleading demonstration.

Keep the recording legible and complete from launch. Use iOS screen recording or QuickTime's wired device capture, not a simulator or animation. Review for personal information. Upload to an Apple-accepted attachment location or a stable reviewer-accessible video URL, verify access without your personal login, and add the same evidence and responses to App Review Information Notes. Do not claim completion until footage is attached.

## Physical QA checklist

- [ ] Cold launch, repeat launch, background/resume and rotation on iPhone/iPad; no crash or clipped controls.
- [ ] Hand readability, tap targets, discard immediacy, draw sorting, all public melds/flowers, long central discard pools.
- [ ] Every offered claim is legal; pass/過水, 叮 lock, flowers, kongs, exchanged opening wins and game completion work.
- [ ] Compare several real end-hand receipts to the configured rules, including base/dealer, pulls/kicks and immediate bonuses.
- [ ] Local records persist correctly; policies remain readable offline and web links open correctly.
- [ ] Nearby permissions granted/denied, invitation cancellation, host loss, timeout, reconnection and 2/3/4 human play.
- [ ] Game Center production entitlement, invite and automatch on signed devices; no unconfigured party-code UI.
- [ ] VoiceOver/Larger Text and performance assessed before declaring accessibility labels or high-frame-rate claims.
- [ ] No enabled ads, purchase controls, debug scenarios or internal developer commentary in Release.
- [ ] Fresh install, upgraded install, storage pressure and airplane-mode single-player.

## Evidence record

| Item | Value |
| --- | --- |
| App Store Connect app ID | 6825805178 |
| Version / build | 1.0 / 1 archived candidate; development re-signed for physical XCTest |
| Physical iPhone / OS / result | iPhone 18 Pro Max, iOS 27.2 RC (24B115), 2026-10-22: 11 integration + 8 gameplay UI + 1 Release walkthrough passed |
| Physical iPad / OS / result | Pending |
| Multiplayer device tests | Pending |
| Recording URL / attachment | [Clean physical-device video](https://fremxhk.github.io/cuiju-submission/DeviceQA/Cuiju-1.0-1-physical-review.mp4), 109 seconds; link added to preparation notes |
| Recording access verified | Public-link verification recorded after upload; no reviewer login required |
| TestFlight build selected for review | Pending |
| Completed review-response date | Pending |

## Completed iPhone run — 2026-10-22

The user approved testing on iOS 27.2 RC (24B115). Record that exact build; do not describe it as a stable public release. The initial physical run passed all 11 integration tests and seven gameplay UI tests. The remaining ready-declaration test was interrupted by iOS's “Trust This Computer?” prompt. After the user approved trust, the targeted rerun passed. One screenshot-only opt-in test was intentionally skipped.

The archived 1.0 (1) Release app was copied and re-signed with the existing development profile solely for installation by XCTest. The executable's `__TEXT` code/constants sections and bundled resources were compared with the submitted archive and matched. This is Release-code device testing, not a TestFlight installation or production Game Center verification.

The additional Release walkthrough passed in 116.234 seconds: normal launch, rules/settings, offline privacy, a genuine unseeded single-player hand with seven human-seat discards, winning settlement, base/dealer receipt, next hand, exit and local history. No debug fixtures were used. The test source is `UITests/ReleaseDeviceFlowTests.swift`; the only integration-test adjustment uses the app's sandbox temporary directory for a rendered atlas, replacing a Mac-specific `/private/tmp` path.

The raw video remains local at `build/PhysicalQA/Cuiju-1.0-1-iPhone-27.2-XCTest-raw.mp4`. It includes private Home Screen/Live Activity content and has rotation/capture defects in some screens. It has **not** been published or presented as Apple's finished demonstration. A clean recording with private overlays suppressed and readable orientation must replace it. Physical iPad, multi-device nearby/production Game Center, TestFlight installation and accessibility coverage remain pending. Sanitized results: `DeviceQA/2026-10-22-results.json`; raw device identifiers/logs are not published.

## Clean review video — 2026-10-22

A clean copy is prepared from the genuine physical Release walkthrough: [Cuiju-1.0-1-physical-review.mp4](https://fremxhk.github.io/cuiju-submission/DeviceQA/Cuiju-1.0-1-physical-review.mp4). It starts with the actual app loading and continues through lobby, rules/privacy, a real offline hand, settlement including base/dealer, and history. Only the unrelated 7.1-second Home Screen lead-in and system safe areas were removed; orientation and letterboxing were normalized. Gameplay remains continuous. The raw file stays private. This supersedes the earlier raw-capture privacy/orientation warning for the published copy. File hash and editing provenance are in `DeviceQA/review-video.json`. It is offline functionality evidence, not a claim of multiplayer or TestFlight coverage.

TestFlight: build 1 is READY_FOR_BETA_TESTING; private internal group “Cuiju Physical QA” and bilingual test instructions prepared. Automatic build notifications disabled. The device's signed-in account matches the App Store Connect owner. Invitation/installation and exact TestFlight QA remain pending the user's requested confirmation; no invitation has been sent yet. XCTest will use documented `UseDestinationArtifacts` mode to test the installed build without reinstalling a development build over it.
