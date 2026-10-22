# Purchase review screenshots

Native shipping SwiftUI views rendered in the dedicated iOS simulator using the bundled StoreKit Test configuration and its real configured USD prices. The opt-in capture test supplies a 50-oil flask fixture so the conditional offer is visible. No real customer save or physical-device evidence is represented.

Regenerate with the shared `StoreReview` test plan, selecting `LightkeeperTests/StoreReviewArtifactTests`, on a dedicated iPhone simulator. The default `Lightkeeper` test plan skips this artifact test. The test writes native, uncomposited images into this directory. Inspect every image before uploading.

```
xcodebuild -project Lightkeeper.xcodeproj -scheme Lightkeeper -testPlan StoreReview \
  -only-testing:LightkeeperTests/StoreReviewArtifactTests \
  -destination 'platform=iOS Simulator,name=Lightkeeper Store iPhone' test
```

`harbor-0` shows oil bundles; `harbor-1` the filled flask; `harbor-2` the subscriptions; `harbor-3` the lighthouse unlock. `themes-0/1/2` show Dusk/Aurora/Storm; `season-0` shows the premium season track. Subscription trial eligibility may differ per account. Verify actual sandbox purchasing, restoration and Apple-localized prices on the physical device later.
