# IndieSuite consumer workflow guide

Applies to the consumer expansion candidates: VaultGlass 5, BioPulse Local 7, ClauseShield 4, DeductGlass/EchoBrief/NutriLoupe/TorqueShield 3, RecallGlass 4. These builds are under validation; this guide is not a claim that they have been released.

All eight apps work without creating a developer account. Document recognition and supported generation happen on device. The six non-health apps support optional private iCloud synchronization with a durable local cache. BioPulse Local and NutriLoupe keep health records on device, without automatic CloudKit synchronization. An internet connection is needed for Apple purchases and iCloud transport. On-device model or speech availability depends on the device, language and system configuration. The supported text workflows remain available when a model is unavailable.

## Saved records, backups and Pro

- Use the library's Search field to match multiple words across supported record fields. Clear it to return to the full library. VaultGlass's archived items are separate from active inventory and can be restored from Insurance Ledger.
- The five newer apps have **Backup & Privacy** in the navigation toolbar. The first three retain their Settings/Backup tab. **Export Complete Archive** includes the app's stored model records, linked children and supported attachments. BioPulse Local and NutriLoupe require a passphrase of at least 12 characters for complete archives. For the other apps a password enables authenticated encryption; leaving it empty produces a plain archive. Save it somewhere you trust.
- Each complete archive is limited to 100 MB. The app rejects an export above the supported import size instead of creating an unusable backup. Large receipt/document collections must stay within this documented bound. PDF and CSV exports are reports, rather than a substitute for the full archive.
- **Import and Merge Archive** adds records whose identifiers are new. Existing identifiers keep their current edits. It does not overwrite an edited record with an older copy. Enable **Use preferences from backup** only if you want to replace supported preferences, such as avoidance ingredients or clinician-preparation settings. Wrong-app, unsupported-version, damaged/password-mismatched and structurally invalid files must fail without a partial merge. Keep the password: there is no recovery service. Preserve the original archive if an import fails.
- Swipe-to-delete asks for confirmation and also removes linked entries through the app's cascade rules. Cloud synchronization can propagate that deletion. Export a backup before deleting records you may need again. VaultGlass Archive is recoverable through its ledger.
- Each app includes five successful AI actions **in total**, rather than five per day/month. Failed/canceled actions release their reserved slot. Reading/editing saved records, library search and backups do not require Pro. Manual Recall cards do not consume AI actions. Pro removes the generation quota; it does not purchase clinical, legal, tax or vehicle expertise.
- Each app's purchase is separate. US launch prices are $0.99/month, $5.99/year or $14.99 once for lifetime. Apple displays the applicable price, eligibility and renewal terms. Lifetime is offered before subscription options. Manage a recurring plan through Apple's subscription settings. Previously owned lifetime access continues to work with the same product identifiers.

## VaultGlass

1. Use **Scan** to acquire a receipt or the labeled sample. Check the extracted item name, merchant, amount, date, serial/model and policy assumptions against the receipt.
2. Open the item to correct details, attach evidence and prepare a claim draft for a real issue. Verify merchant/manufacturer/card terms before relying on estimated dates. A generated draft is not automatically sent.
3. Use search, pinning and property/room filters to organize active inventory. Changing the property resets the room filter.
4. Export the Insurance Ledger PDF using the displayed valuation assumptions. Archive a returned/disposed item; restore it from **Archived / Returned** if needed.

Amounts are USD. Numeric slash dates use US month/day interpretation when ambiguous. Dates, coverage, depreciation and claim outcomes require verification.

## BioPulse Local

1. Use **Import Labs**, specify age/date and acquire your report. Open **Review Panel** and compare supported markers, source values and units with the original laboratory document.
2. Use **Correct source value** when a supported value/unit is wrong. Edits remain staged until **Save correction**. Invalid values/unsupported units are rejected. Saving recalculates normalized values and affected saved estimates and clears the earlier generated summaries.
3. Search panel history by provider, collection date or supported marker names. Use a panel's context menu to delete an accidental import, then confirm the deletion.
4. Use Correlation Studio for historical measurements, optional read-only Apple Health comparisons and dated lifestyle notes. Use Doctor Brief to prepare neutral clinician questions and export your records.

This is an educational organizer. It does not support every possible laboratory marker or unit and is not a diagnostic service. Illustrative reference ranges and PhenoAge estimates are not individualized clinical thresholds. Follow your clinician/laboratory's instructions.

## ClauseShield

1. Choose the relevant role and category, then import an agreement. Screening identifies source-linked flags and specified missing-protection checks; it does not establish completeness or enforceability.
2. Read the original quote and proposal. **Edit proposed wording** lets you stage your own replacement. **Save wording** preserves the original quote and decision. An already accepted proposal updates the draft immediately; otherwise select **Use replacement** to include it. Dismiss a flag or reset a decision when appropriate.
3. Import a revised version to inspect paragraph differences. Prepare your negotiation draft or PDF memo, then review the final wording with qualified counsel before using it.
4. Search prior audits by title, counterparty, category or source text. Confirm any deletion. Use Backup & Privacy for portable recovery.

The app does not send a reply, sign an agreement or provide jurisdiction-wide legal advice.

## DeductGlass

1. Add a receipt, CSV or source text. Review merchant/date/amount/category and enter the business purpose and any relevant attendees before marking evidence verified.
New records retain their source calendar date when the device time zone changes. Earlier records offer **Confirm calendar date** after you verify the receipt; their original stored timestamp is retained.
2. Select tax year and jurisdiction in **Tax profile & method comparison**. If multiple saved plans arrive through backup/iCloud, use **Active workspace** to choose the assumptions; saved plans are not silently overwritten.
3. US comparisons use the explicit year/distance/cost assumptions. Singapore is a separate recordkeeping workflow; US formulas do not apply to it. Stored amounts are USD, with no currency conversion.
4. Export the selected year's evidence PDF or **selected-year CSV**. CSV text is quoted and potentially executable spreadsheet cells are prefixed with an apostrophe. Attachments belong in complete backups.
5. To import CSV, include `merchant,date,amount,category`; optional `purpose,attendees,currency` columns are supported. Header names are case-insensitive and may be quoted/reordered. Use `YYYY-MM-DD`, nonnegative amounts and USD currency. UTF-8 BOM, LF/CRLF/CR line endings, quoted commas, doubled quotes and embedded quoted newlines are supported. Rows must match their header width. Imported rows require fresh verification; CSV does not restore prior verification or attachment data.

Example:

```csv
merchant,date,amount,category,purpose,attendees,currency
"Example Store",2026-10-12,25.50,Supplies,"Office stationery",,USD
```

These are recordkeeping tools and estimates for professional review, not filed returns or deduction guarantees.

## EchoBrief

1. Start a meeting brief. Paste a transcript or use supported on-device audio capture/import after obtaining participant consent. Edit the transcript before analysis and enter the actual meeting duration, attendance and hourly-cost assumptions.
2. Review the brief. **Edit title & summary** lets you correct the saved summary while preserving the original transcript, commitments and cost assumptions.
3. Open each commitment and check its owner/task/source wording. Set a due date yourself when the source only gives relative wording. Confirm the task before explicitly adding it to your system Reminders or Calendar. The app does not message participants.
4. Export the meeting PDF or a complete archive. Canceling a nonempty composer asks whether to keep editing or discard it; swiping does not silently discard the draft.

Speech recognition requires supported on-device recognition. Temporary capture is removed when the composer closes; an exported archive preserves saved transcript records, rather than a permanent audio recording.

## NutriLoupe

1. Enter your ingredients to avoid, then scan/paste a label. Check the original ingredient wording. Avoidance matches are limited text matches, not allergen detection or a safety certificate.
2. **Correct label or journal time** stages corrections and recalculates local ingredient matches and the preference heuristic when saved. A journal time cannot be in the future or later than an already linked symptom.
3. Log observations with symptom name, severity and time. Swipe an incorrect symptom entry to delete it after confirmation. **Log this meal again now** creates a separate record/time with no inherited symptoms; open the new journal record to add its own observations.
4. Explore 14-day association counts, their uncertainty and reporting limitations. Export the meal/symptom CSV (including meals with no recorded symptoms), PDF association summary or complete archive.

The score is an unvalidated preference heuristic; ingredient-based processing classification is provisional. Associations do not establish causes. The app does not diagnose, prescribe an elimination diet or replace professional assessment.

## TorqueShield

1. Import an itemized estimate. Supported text format is `Service | Parts: $100 | Labor: $80`. Compare every extracted line and amount against the original estimate.
2. **Correct quoted facts** stages a service/parts/labor correction. Saving updates the displayed quote and resets the explanation to a correction notice while keeping the original estimate, saved decision and optional comparison quote.
3. Record a review/approve/decline decision. Add a benchmark only when you have a real comparable quote, source/date and matching scope. Export the repair review and questions for the shop.
4. Open VIN & lease workspace, enter your own vehicle and lease assumptions, and verify them against the lease. If multiple saved vehicle profiles arrive, choose **Active vehicle**. The checksum/model-year cycle is not a history, ownership or safety lookup.

The app does not fetch repair-market prices, certify vehicle safety or include omitted lease taxes/fees/condition charges in its estimates.

## RecallGlass

1. In Study, create cards from your own source material or use **Create empty deck without AI**. Add a manual card with its question, source-backed answer and key concepts.
2. Use **Edit card** from the review screen (or card context menu) to correct content. History and schedule remain unchanged unless you explicitly enable **Reset review schedule**. Invalid/empty edits are not saved.
3. Recall before revealing the canonical answer. Review suggested feedback, then choose the final Again/Hard/Good/Easy grade yourself. The learner's confirmed grade controls scheduling.
4. In Speak, create cue cards from your manuscript, edit the saved cues and rehearse with the timer. Choose paper/card dimensions, cut marks and font scale, preview the full PDF, and print at actual size after checking printer margins.
5. Search the Study/Speak libraries and export a complete archive to preserve scheduling history, relationships, cue text, timing and layout choices. Confirm card/project deletions; unfinished composers require explicit discard.

Generated content/feedback needs source review. The app supplies no third-party study library and does not certify the factual correctness of manually entered material.

## Problems and recovery

- **No saved results visible:** clear Search, check active/archived views and workspace/year filters, and confirm the iCloud account on the device. Do not delete the app or its local cache as a first troubleshooting step.
- **Import failed:** check file type/size, required source facts, supported CSV shape and supported units. Correct the source or use the documented text format. A failed action must not consume a free slot.
- **Model unavailable:** use supported local/text extraction and inspect the result. Language/device/model availability is not a paid entitlement and buying Pro cannot enable unsupported system features.
- **Backup rejected:** check the app identity, version, password and 100 MB bound. Preserve the file; repeated imports merge identifiers rather than replacing newer edited records. Password recovery is unavailable.
- **Cloud appears delayed in a non-health app:** changes remain in the durable local cache. System-managed CloudKit sync is asynchronous and may be deferred by connectivity, account restrictions or OS scheduling; there is no promise of immediate transport. See [the separately qualified production evidence](ProductionServiceResults.md).
- **Purchase products unavailable:** use Reload Products and check the App Store account/connectivity. Never display a fabricated cached price or claim access before a verified Apple entitlement. Saved records remain usable without a new purchase.

For support, use the app's Support link and provide app/build, OS, device model and steps. Avoid sending private documents or medical/financial information unless specifically needed and requested.
