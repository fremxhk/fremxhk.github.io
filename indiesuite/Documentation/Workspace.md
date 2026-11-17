# Local development workspace

The development checkouts moved to the connected Xcode SSD on 17 November 2026.

| Checkout | Physical location |
| --- | --- |
| App source, build products, archives and test evidence | `/Volumes/XCode/Developer/IndieSuite` |
| Published documentation and website | `/Volumes/XCode/Developer/fremxhk.github.io` |

The previous `~/Developer/IndieSuite` and `~/Developer/fremxhk.github.io` paths are compatibility symlinks. Run development commands from the physical SSD checkout so subsequent project-local build products and test results stay there. Keep the drive connected while working.

Before removing the internal duplicate copies, verification compared SHA-256 file contents, symlink targets, permission modes and Git state. IndieSuite matched across 59,345 entries, including 55,405 regular files; the public documentation checkout matched across 484 entries, including 417 regular files. Migration preserved source commit `d1d1654` and public commit `c6c848b`; subsequent commits are separate. The full integrity report remains local in `.private/workspace-migration.json`.

Internal free space measured 16.88 GiB at the completed migration checkpoint. The physical-device hold marker was preserved. No physical device was used. Sequential simulator QA continues from this checkout; migration itself is not an app test result.
