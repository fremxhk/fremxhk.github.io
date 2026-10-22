# Guideline 2.1 — App Review notes and response draft

**DRAFT — DO NOT SEND OR SUBMIT.** Replace the evidence fields after testing the exact submitted build on physical devices. Copy the finalized six answers into both the Resolution Center reply and App Review Information → Notes. Private reviewer name, phone and email belong in App Store Connect only.

Build/version: 1.0 (1), uploaded and processed for TestFlight; confirm the final production selection after QA.
Physical device / latest public iOS version / test date: PENDING.
Recording URL (accessible without credentials): PENDING.

## 1. Physical-device screen recording
Pending device availability. The recording will begin by launching the exact submitted build and show onboarding, a solved puzzle, undo, a hint, the daily beacon, a shared Duet, keepsakes and paid-feature access, purchase and restore. Follow `recording-script.md` and verify playback without login. Simulator screenshots are not a replacement.

There is no developer account registration, login or account deletion flow. Optional Apple Game Center/iCloud accounts use system interfaces. Duet links contain player-created structured puzzle state, move count and elapsed time. There is no public feed, arbitrary text/media upload, chat, player discovery or hosted user-content service. No in-app blocking/reporting flow exists; disclose this explicitly rather than claiming moderation features. Resolve any reviewer concern about this share-link model before submission.

## 2. Purpose and target audience
Lightkeeper is a general-audience native iPhone/iPad logic-puzzle game for people who enjoy calm, short reasoning challenges. Players place lanterns to illuminate every open square, prevent lanterns from shining at one another, and satisfy exact adjacency numbers on posts. A guided interactive walkthrough teaches the rules. Campaign puzzles, daily beacons and optional shared Duet puzzles provide recurring play; cosmetic collections reward progress. Every puzzle is solvable without paid hints. It is not intended for business-only distribution, gambling or a regulated professional service.

## 3. Access and setup
No demo credentials, registration or sample files are needed. Launch → complete or skip the walkthrough → Journey → first island → first puzzle. Tap open squares to add/remove lanterns; use Undo and the hint control. Replay via Settings → Replay guided walkthrough. Coast contains the daily beacon; Duet creates/opens share links; Keepsakes shows collected items; Harbor shows purchases and restore. Optional Game Center/iCloud can be reached from Settings. Basic bundled puzzles work offline; downloads, purchases and optional Apple services require network/account availability. Record actual production pack and commerce validation before making those features available for review.

## 4. External services, tools and platforms
Core puzzle generation, rules and save behavior run locally. Apple StoreKit handles payments, subscriptions and verified entitlements; GameKit provides optional Game Center authentication/leaderboards; GameSave/iCloud provides optional save sync; Background Assets delivers Apple-hosted island packs once provisioned. WidgetKit, ActivityKit, App Intents and local notifications provide device features. GitHub Pages hosts privacy/support documents; email handles support. AppLovin MAX and TelemetryDeck dependencies are registered in the project but excluded from the shipping binary. No ads, tracking, telemetry, Foundation Models calls or developer-hosted backend are active. See `services-and-privacy.md` and reconcile the final signed build before submission.

## 5. Regional behavior
The core puzzle rules and content have no app-defined regional restrictions. Interface text is currently English. Daily puzzles and the daily leaderboard reset together at 00:00 UTC. Personal streaks use the device's local calendar/time zone. StoreKit prices/currencies, product availability, introductory-offer eligibility, Game Center/iCloud and other Apple services depend on the storefront, account and Apple availability. 146 storefronts are configured. EU storefronts are disabled pending DSA verification; China mainland and Vietnam are excluded pending game-specific licensing.

## 6. Regulated services and protected material
The app does not provide regulated medical, financial, gambling or other professional services. Puzzles are generated offline by the project's own tooling; the interface uses native rendering and bundled project assets. No third-party media or puzzle-provider feed is required for core play. The signed-archive inventory is recorded in PRIVACY_AND_RIGHTS_AUDIT.md; re-audit any replacement archive. No regulatory credentials are applicable to the stated puzzle functionality.
