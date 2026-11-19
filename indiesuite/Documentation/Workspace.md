# Local development workspace

The development checkouts moved to the connected Xcode SSD on 17 November 2026.

| Checkout | Physical location |
| --- | --- |
| App source, build products, archives and test evidence | `/Volumes/XCode/Developer/IndieSuite` |
| Published documentation and website | `/Volumes/XCode/Developer/fremxhk.github.io` |

The previous `~/Developer/IndieSuite` and `~/Developer/fremxhk.github.io` paths are compatibility symlinks. Run development commands from the physical SSD checkout so subsequent project-local build products and test results stay there. Keep the drive connected while working.

Before removing the internal duplicate copies, verification compared SHA-256 file contents, symlink targets, permission modes and Git state. IndieSuite matched across 59,345 entries, including 55,405 regular files; the public documentation checkout matched across 484 entries, including 417 regular files. Migration preserved source commit `d1d1654` and public commit `c6c848b`; subsequent commits are separate. The full integrity report remains local in `.private/workspace-migration.json`.

Internal free space measured 16.88 GiB at the completed migration checkpoint. The physical-device hold marker was preserved. No physical device was used. Sequential simulator QA continues from this checkout; migration itself is not an app test result.


## Reproducing the consumer simulator checks

Use dedicated simulator fixtures with the real free allowance available. These runners control only simulator IDs supplied by the caller, use two build jobs and disable parallel test destinations. The native capture runner uses Release, runs all 13 methods on phone then tablet, and expects distinct profiles; it does not erase their data. Stop the previous task-owned simulator before switching to another runner.

- `Scripts/test-sequential.sh SIMULATOR_UDID`: the original-app/evaluation group, 52 distinct methods (33 evaluations, 15 UI and four additional app-qualified purchase methods). The five StoreKit methods use separate host launches; the remaining 28 evaluations run separately.
- `Scripts/capture-batch2-store-assets.sh IPHONE_SIMULATOR IPAD_SIMULATOR`: 13 newer-app Release UI methods on each native profile. Repeated profiles do not increase the unique count.
- `Scripts/run-batch2-purchase-qa.sh SIMULATOR_UDID`: five newer-app purchase methods.
- `Scripts/run-batch2-cloud-readiness.py SIMULATOR_UDID`: 20 offline storage methods in five app hosts.
- The `IndieSuiteSequentialQA` scheme supplies the 31 core methods. Use the chosen simulator, `.build/ConsumerCore`, two jobs and parallel testing disabled, separately from the other runners.

Each updated runner records application/configuration/test SHA-256 inputs and verifies they stayed unchanged. `Scripts/verify-qa-result.py RESULT.xcresult EXPECTED_COUNT` rejects incorrect counts, failures, skips and the blocking audio-session warning. Isolated defaults are `.build/ConsumerStudioUI`, `.build/ConsumerPurchases`, `.build/ConsumerEvaluations` and `.build/ConsumerStorage`; older shared build outputs are not a validation prerequisite. Production synchronization and distribution verification remain separate checks.

For repeated simulator-system crashes under concurrent machine load, set `INDIESUITE_QA_ISOLATE_UI=1` on either the native capture runner or `test-sequential.sh`. The same selected simulator cold-boots before each complete UI method. `Scripts/run-ui-method-cohort.py` retains every individual bundle, verifies the exact target/class/method plus unchanged inputs and zero failures/skips, then uses Apple's `xcresulttool merge` only after all 13 or 15 required methods pass. It does not retry or merge failed/partial inputs. App data and the free-use allowance persist between methods; no erase or entitlement override occurs between cases. A tool-level fixture check verified preservation of four exact method identities and all 18 PNG attachments byte for byte; that historical fixture check is separate from app release evidence.
