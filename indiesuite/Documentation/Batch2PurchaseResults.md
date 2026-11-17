# Five-app simulator purchase results

**Five distinct target-qualified UI methods passed, with zero failures or skips in the listed bundles.**

Executed sequentially on one iPhone 17e simulator, iOS 27.0, using Xcode 27.2. Parallel testing and simulator clones were disabled. Each app used its own bundled Xcode StoreKit configuration and a local SKTestSession. No real payment or physical device was used.

| App | Passing method | Evidence |
| --- | --- | --- |
| DeductGlass | `DeductGlassPurchaseUITests/Batch2PurchaseFlowTests/test01ThreeLocalPlansAndLifetimeRelaunch` | `TestResults/Batch2-Purchases-20261117-200206/DeductGlass.xcresult` |
| EchoBrief | `EchoBriefPurchaseUITests/Batch2PurchaseFlowTests/test01ThreeLocalPlansAndLifetimeRelaunch` | `TestResults/Batch2-Purchases-20261117-200206/EchoBrief.xcresult` |
| NutriLoupe | `NutriLoupePurchaseUITests/Batch2PurchaseFlowTests/test01ThreeLocalPlansAndLifetimeRelaunch` | `TestResults/Batch2-Purchases-20261117-200206/NutriLoupe.xcresult` |
| TorqueShield | `TorqueShieldPurchaseUITests/Batch2PurchaseFlowTests/test01ThreeLocalPlansAndLifetimeRelaunch` | `TestResults/Batch2-Purchases-20261117-200206/TorqueShield.xcresult` |
| RecallGlass | `RecallGlassPurchaseUITests/Batch2PurchaseFlowTests/test01ThreeLocalPlansAndLifetimeRelaunch` | `TestResults/Batch2-Purchases-20261117-200206/RecallGlass.xcresult` |

Each method verifies:

- Monthly and annual plan selection and displayed plan details.
- Local purchase of each subscription and the resulting active Pro state.
- A separate lifetime offer and successful local lifetime purchase.
- Active entitlement persistence after terminating and relaunching the app.
- Subscription management access and suppression of duplicate purchase offers while active.
- Privacy Policy and Apple Standard License links in the purchase UI.

Four native opaque RGB screenshots per app are in [the purchase evidence folder](Previews/Batch2/Purchases). These screenshots show local StoreKit simulation, not live App Store pricing delivery or payments. They use no forced Pro entitlement.

Two earlier DeductGlass attempts failed because the harness queried lazy-list footer controls before scrolling them into view. The harness was corrected with bounded scrolling before waiting; those failed attempts remain private and are excluded from the passing inventory. App runtime source was unchanged.

These five methods are separate from the main regression, eight-app pipeline and five studio workflow inventories. Repeated executions are not additional distinct tests. Production iCloud synchronization, physical audio/calendar/printer behavior and live App Store transactions are outside this evidence.
