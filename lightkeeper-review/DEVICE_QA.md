# Physical iPhone QA — 2026-10-23

Device: iPhone 18 Pro Max, iOS 27.2, build 24B115. The owner identifies this as the release candidate and explicitly approved using this OS. Developer tooling reports the release channel as Beta; no OS change is requested.

The development-signed 1.0 (1) app has passed **24 tests on the physical device**: 3 StoreKit Test checks, 20 app/functionality tests and one interactive UI walkthrough. One opt-in screenshot test was skipped. StoreKit Test covers the product catalogue, verified entitlements and restore, and a purchase followed by explicit acknowledgement. These local test transactions require no Apple ID authentication and do not validate the TestFlight sandbox storefront.

The first purchase run failed because the normal app host was concurrently consuming the unit tests' transactions. The Debug test host now uses an isolated in-memory composition, configured explicitly by the test plan. The three purchase tests then passed. This host isolation does not change the Release binary.

The package suites were already verified on the simulator; Xcode does not support their unhosted runner on physical destinations. They are not counted as physical-device tests.

Private result bundles: `/tmp/Lightkeeper-device-iap-isolated.xcresult` (3 passed) and `/tmp/Lightkeeper-device-functional.xcresult` (20 passed, 1 skipped). These paths are local evidence, not public downloadable files.

`Tools/DeviceQA` is an independent UI test runner that can launch the installed app by bundle ID. It leaves purchase confirmation and credentials to the owner. Walkthrough gestures are short and slow. The native Control Center recording was captured successfully and exported through a PhotosPicker helper that accessed only the selected recording. The helper was then removed from the phone.

Still required: approved TestFlight-copy purchasing/restore and Apple-hosted pack delivery; optional Game Center and two-device iCloud integration checks where credentials/devices are needed; a final exact-TestFlight recording covering launch, purchase and restore. Production review remains an unsubmitted draft.

## Recorded evidence

[Watch the physical-device walkthrough](https://fremxhk.github.io/lightkeeper-review/device-walkthrough.html). The 123-second continuous app excerpt shows the interactive lessons, a solved campaign puzzle, undo, hint and feature/shop navigation. Private Home Screen and Control Center lead/tail footage was trimmed. This development-signed 1.0 (1) recording is supplemental QA evidence; it does not demonstrate TestFlight purchase authentication or replace the final launch-to-purchase recording. The raw original remains private.

Final simulator regression: **100 passed, 0 failed, 1 optional screenshot test skipped**. Physical UI walkthrough: **1 passed**, including seven lessons, L001 solve, undo and hint. Hosted-pack delivery, Game Center and two-device cloud checks remain unverified.
