# Physical-device QA and Guideline 2.1 recording

Status: **pending — no physical device currently available**. Simulator UI captures and the 100,000-hand engine audit are supporting evidence only. Do not submit for review with pending evidence or paste the unfinished response as if testing had occurred.

## Record the exact candidate

Install the signed candidate using TestFlight when available. Record version/build, device model, latest public OS version, date, and whether it is the same build selected in App Store Connect. Re-test after any binary change. Test at least physical iPhone and iPad because both platforms are supported; use the latest public OS for the requested video, and cover minimum-supported OS and a small iPhone as device access permits.

## Video shot list

1. Start screen recording on the physical device with the app closed. Launch from the Home Screen, showing the actual app icon and lobby.
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
| Version / build | 1.0 / 1 (candidate; confirm exact uploaded build) |
| Physical iPhone / OS / result | Pending |
| Physical iPad / OS / result | Pending |
| Multiplayer device tests | Pending |
| Recording URL / attachment | Pending |
| Recording access verified | Pending |
| TestFlight build selected for review | Pending |
| Completed review-response date | Pending |
