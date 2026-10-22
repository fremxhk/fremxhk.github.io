# Submission questionnaire worksheet — 1.0 free release

Prepared 2026-10-22 from the SDK-free `project.yml` build. Answers must be reconfirmed against the exact uploaded binary and actual operating practices.

## App Privacy

Proposed answer: **No, we do not collect data from this app**, subject to the account holder's confirmation that no additional server, SDK or data collection is introduced. Apple defines collection as off-device transmission accessible to the developer/partners beyond servicing the request in real time. Local SwiftData records and UserDefaults remain on-device. Optional peer transport shares names/identifiers and full game state for multiplayer; there is no developer-operated service, telemetry, analytics or ads SDK. Apple Game Center and device backup operate under Apple's settings and policies. Voluntary support email is used only to service requests; evaluate Apple's optional disclosure criteria if support practices change.

No tracking; no advertising identifier access. The privacy manifest declares UserDefaults reason CA92.1 for settings and a local nearby identity, with no developer-collected data. The bundled policy and public app-specific policy disclose the multiplayer transport and local records. Do not substitute the portal's generic advertising policy.

Public privacy URL: https://fremxhk.github.io/cuiju-privacy.html
Support URL: https://fremxhk.github.io/cuiju-support.html

## Age rating and content

Do not assume 4+ merely because no money is involved. The app has a Mahjong scoring/debt/settlement system. Conservative proposed questionnaire answer: **Frequent simulated gambling**, **no real-money gambling**, **no loot boxes**, no advertising, violence, sexual content, substance references or medical content. Competitive gameplay is present; evaluate the contest question from the current questionnaire. There is no app-provided chat, unrestricted browser or user-posted media; Game Center display names/avatars are Apple-managed identity.

Apple distinguishes simulated gambling (wagering without redeemable money) from gambling. The points are not staked/purchased, so disclose the actual scoring flow in Review Notes and request clarification if App Review classifies it differently. Let App Store Connect compute the final rating; current definitions assign frequent simulated gambling an 18+ global rating, with region-specific restrictions. Do not select Kids Category. For Korea, obtain any required classification number before enabling distribution if this answer is used. Select storefronts deliberately rather than accepting worldwide availability without checking regional eligibility.

## Export, commerce and accessibility

`ITSAppUsesNonExemptEncryption = false`: app uses Apple system transport encryption (MultipeerConnectivity/GameKit), no custom cryptography. Reassess if transport or dependencies change; this is a technical worksheet, not a completed legal filing.

Version 1.0: free; no purchasable products to submit. Use Apple's standard EULA unless you explicitly choose a custom agreement. Account holder must complete agreements, review-contact phone/name/email, territorial availability, EU trader-status verification if applicable, and any regional game approvals.

Do not claim VoiceOver, Larger Text, reduced motion or other Accessibility Nutrition Labels until the feature meets Apple's criteria on real devices. Existing accessible controls and tests are not a complete certification.

## Official references checked

- [App Privacy definitions and optional disclosure](https://developer.apple.com/app-store/app-privacy-details/)
- [Manage privacy answers](https://developer.apple.com/help/app-store-connect/manage-app-information/manage-app-privacy/)
- [Age-rating definitions and regional ratings](https://developer.apple.com/help/app-store-connect/reference/app-information/age-ratings-values-and-definitions/)
- [Review guidelines, including privacy-policy access](https://developer.apple.com/app-store/review/guidelines/)
- [Submission overview and current SDK requirements](https://developer.apple.com/app-store/submitting/)
- [Screenshot specifications](https://developer.apple.com/help/app-store-connect/reference/app-information/screenshot-specifications)
