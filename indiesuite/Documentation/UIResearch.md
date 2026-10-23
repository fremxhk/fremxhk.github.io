# UI research and design decisions

Research date: 23 October 2026. Scope: the three native iOS apps in this workspace. This is a literature and platform-guidance review, followed by design hypotheses and implementation. It is not a user-interview study or evidence of measured retention improvement.

## Product goal

Make returning worthwhile when the user has a real task: a purchase to protect, a lab result to understand, or an agreement to negotiate. A longer session or a daily open is not automatically a better outcome. VaultGlass and ClauseShield are often episodic tools; BioPulse should follow the user's actual care and testing schedule.

## Evidence informing the design

**First value should come from doing.** Apple's onboarding guidance recommends interactive, contextual instruction, optional onboarding and delayed nonessential setup. Applied here: no mandatory introductory carousel, account creation or purchase gate before trying the core task. Empty states explain the result and provide one clear import action; synthetic examples remain available in the scanner. [Apple: Onboarding](https://developer.apple.com/design/human-interface-guidelines/onboarding).

**Glass should clarify functional layers.** Apple's materials guidance distinguishes Liquid Glass navigation and controls from content surfaces. It recommends restrained use, appropriate contrast and standard materials for reading content. Dense lab values, clauses and inventory records now use standard material cards; the floating QA control uses the reusable card's Liquid Glass mode. Navigation, tabs and sheets retain native system styling. Reduce Transparency and increased contrast have explicit fallbacks. [Apple: Materials](https://developer.apple.com/design/human-interface-guidelines/materials).

**Charts need a question and readable detail.** Apple recommends simple initial charts, gradual disclosure, explanatory text and accessible alternatives. BioPulse now leads with a selected marker and a factual change summary. The health overlay is optional, and a disclosure reveals the chart's saved lab values in text. The comparison retains labeled axes and different line treatments when enabled. [Apple: Charting data](https://developer.apple.com/design/human-interface-guidelines/charting-data).

**Notifications should earn attention.** Apple favors timely, concise, high-value information and discourages repeated notifications for the same event. VaultGlass uses actual return and warranty dates. These UI changes add no promotional reminders, daily reactivation messages or app-icon score badges. The deadline is visible inside the app as well. [Apple: Notifications](https://developer.apple.com/design/human-interface-guidelines/notifications).

**Personal relevance and competence matter.** A July 2026 overview of nineteen reviews describes autonomy, competence and relatedness as useful mechanisms for interpreting health-app engagement. It also reports inconsistent engagement definitions and heterogeneous evidence. This supports a hypothesis of user-chosen focus, clear feedback and clinician preparation in BioPulse; it does not establish a retention effect for these apps. Applying the same approach to inventory or contracts is a design inference. [Baykoca et al., JMIR mHealth and uHealth, 2026](https://mhealth.jmir.org/2026/1/e88382).

**Feedback and monitoring are promising, with limits.** A 2023 systematic review of twenty-eight studies associated several behavior-change techniques, including goal setting, self-monitoring, feedback and prompts, with engagement. It could not establish consistent links with each component of engagement. We use visible task progress and personal history, while leaving out arbitrary points, leaderboard comparisons and streak loss. These choices require usability validation rather than a claim of proven retention. [Frontiers in Psychology, 2023](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2023.1227443/full).

## App-specific design

| App | First useful experience | Reason to return | Implemented presentation |
| --- | --- | --- | --- |
| VaultGlass | Turn one receipt into a record | A real return deadline, missing proof, a new purchase or insurance review | A contextual next-action card; proof-of-purchase progress; pinning and priority order; photos and receipt evidence attached in the record |
| BioPulse Local | Import a panel and verify the extracted values | Compare a chosen marker, review an experiment or prepare for a clinician visit | A user-selected focus marker; factual change from the preceding panel; a doctor-brief action; optional health overlay and readable chart values |
| ClauseShield | Review one agreement for the selected role | Continue undecided flags, assess a revised draft or prepare a negotiation | A continue-review entry; reviewed-versus-pending progress; explicit accept/dismiss decisions; a negotiation action after the review is complete |

The shared visual vocabulary uses dynamic type, semantic colors, native controls and restrained cards. Each app has a distinct accent: blue for inventory, teal for labs and indigo for contracts. The hierarchy is action first, essential summary second, detail on demand. Color is reinforced with labels and symbols. No task completion percentage is represented as a clinical outcome, legal clearance or insurance coverage guarantee.

## Interaction details

- Empty states explain what the import will produce and provide a direct action.
- Returning views prioritize a concrete next step over a generic welcome message.
- Progress represents saved evidence or review decisions. It does not reward app opening.
- Processing uses an indeterminate status rather than an invented percentage. Acquisition supports cancellation; incomplete actions are not charged.
- Long model responses have a bounded attempt followed by deterministic extraction, with the route disclosed in QA telemetry.
- Physician preparation and redline drafting remain tools the user controls. Nothing is emailed automatically.
- Chart values and critical statuses remain understandable without color or animation. Native layouts resize and respect accessibility settings.

## Validation protocol

Conduct a moderated task test with representative users before making retention claims. Ask each participant to import a document, identify the next useful step, explain a summary, recover from an input error, and resume a saved task. Observe misunderstandings, assistance needed, completion time and accessibility barriers. Do not use a participant's real medical or contract data unless a separate consent process supports it.

Evaluate meaningful outcomes separately for each app: a receipt saved with usable proof, a verified panel and useful doctor brief, or a completed review with a coherent negotiation memo. Return-use measures should reflect the actual task cadence. A lab user who returns only for the next clinician-agreed test may be succeeding. A contract user who exports a complete memo and leaves may also be succeeding.

The workspace currently performs local QA telemetry only. This research does not add analytics transmission, engagement tracking, participant outreach or a recurring notification campaign. Future measurement should be explicit and consented where appropriate.

## Implemented previews

Native simulator captures: [VaultGlass dashboard](Previews/VaultGlass-Dashboard.png), [receipt result](Previews/VaultGlass-Receipt.png), [BioPulse dashboard](Previews/BioPulse-Dashboard.png), [lab detail](Previews/BioPulse-Panel.png), [ClauseShield playbook](Previews/ClauseShield-Playbook.png), [audit](Previews/ClauseShield-Audit.png), and [negotiation draft](Previews/ClauseShield-Pushback.png). See [Validation.md](Validation.md) for the passing checks and limits.
