# Health-record storage and transfer

Consumer revision decision: 19 November 2026. Applies to BioPulse Local and NutriLoupe. The other six apps retain optional private CloudKit synchronization.

Apple's [App Review Guideline 5.1.3(ii)](https://developer.apple.com/app-store/review/guidelines/#health-and-health-research) prohibits storing personal health information in iCloud. These two apps therefore use on-device SwiftData stores, with no automatic CloudKit mirroring and no iCloud/push entitlement. Their default file-protection entitlement is Complete Protection.

The shared container factory enforces the local-health policy for both app identifiers, including calls from app intents. It opens the previously active cache URL rather than creating an empty replacement. Existing cached records and attachments are preserved. It does not delete existing remote records or retrieve cloud-only records from an earlier beta. No automatic deletion of user data is performed.

Health-data Library/Documents directories request exclusion from system backups. Apple documents the [backup-exclusion resource flag](https://developer.apple.com/documentation/foundation/optimizing-your-app-s-data-for-icloud-backup) as OS guidance, rather than a guarantee about every backup or device migration. Users should keep their own encrypted archive before deleting the app or changing devices. The app does not promise an automatic cloud recovery service.

Complete health archives require a passphrase of at least 12 characters. Passwords are not stored or sent to a developer service, and there is no recovery service. Users explicitly select the destination for a file or report export; exports may contain sensitive information. Legacy plain archives can still be imported locally. Supported preferences are included, but are only replaced when the user enables the import preference option. Purchase entitlements and free-action counters are never restored from an archive.

The earlier automatic-cloud implementation and its development/service experiments remain historical evidence. They do not establish the current local-health policy. The new binaries require their own storage, migration, entitlement, UI and archive checks. BioPulse build 6 was removed from review while this correction is prepared; its version state was read back as Developer Rejected. No replacement was submitted by that action.
