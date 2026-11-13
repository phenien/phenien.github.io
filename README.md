# Paul Henien’s app websites

Static GitHub Pages portfolio and support/privacy pages for Sunday School Manager, CopticLife and Confession Manager. No build step or dependencies are required.

## Brand colours

Shared styles live in `assets/site.css`. Page and portfolio-card theme classes use colours from the app sources:

- Sunday School Manager: blue `#337FF2`, cyan `#33CCD9`; based on `SSmanager/SSmanager/Utilities/ModernTheme.swift` and the Flutter `ModernColors` palette.
- CopticLife: gold `#D4AF37`, slate background `#F1F5F9`; based on `copticLife/CopticLife/Theme.swift` and `copticLife_flutter/lib/core/theme/coptic_theme.dart`.
- Confession Manager: burnt orange `#CC6633`, parchment `#F5EBD6` / `#FCF7ED`, ink `#523621`; based on `ConfessionsManager/Confession Manager/Core/Utilities/ColorScheme+Extension.swift`.

Darker variants are used for text contrast. Update the shared stylesheet when app branding changes.

## Preview and publish

Run `python3 -m http.server 8000` from this directory and open `http://localhost:8000`. Check the homepage, each app page and its privacy policy at desktop and mobile sizes.

Deploy through the repository’s existing GitHub Pages workflow. Local edits do not update the public website until committed and pushed to the publishing branch.

## Content review (13 November 2026)

- Verified Sunday School Manager’s App Store ID (`6755734036`) and Confession Manager’s ID (`6755344059`) against their Apple listings.
- Replaced Sunday School Manager’s placeholder download link and added Confession Manager download links.
- Removed Confession Manager’s stale hardcoded version and unverified fixed upgrade prices.
- No CopticLife App Store listing was found during the review. Its page links to the established developer support address for availability instead of displaying a download badge without a store destination.
- CopticLife’s iOS 17 minimum matches the native project configuration; confirm against the store listing when published.
- Corrected privacy pages against native iOS storage and SDK implementation: Confession Manager uses local JSON, automatic CloudKit sync when available, and AdMob; CopticLife enables iCloud sync by default for new users.
- Removed unsupported security-audit, zero-data-collection, deletion-deadline and advertising guarantees. Advertising descriptions use Google’s SDK disclosure guidance.
- Corrected CopticLife’s Agpeya languages to English and Arabic and placed full Agpeya access under Premium, matching the native paywall. Corrected viewer access to assigned classes.
- The public store listings may lag local app development. No mailbox-delivery test or legal-compliance certification was performed.

### Review sources

- https://apps.apple.com/us/app/sunday-school-manager/id6755734036
- https://apps.apple.com/ca/app/confession-manager/id6755344059
- https://developers.google.com/admob/ios/privacy/data-disclosure
- https://developers.google.com/admob/ios/privacy/ad-serving-modes
- Native app source files: `CloudSyncManager.swift`, `AgpeyaView.swift`, `Models.swift`, `PremiumPurchaseView.swift`, `ConfessionPersistence.swift`, `ReminderPersistence.swift`, `iCloudManager.swift`, `AdMobManager.swift`, and Sunday School Manager’s Firebase services and attendance model.
