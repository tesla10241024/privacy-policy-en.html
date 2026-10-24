# HueLoom privacy review

Reviewed against the current Objective-C source, bundled dependencies, linked frameworks, and `Info.plist`.

## Recommended App Store Connect answer

**Data Collection: No, this app does not collect data.**

This recommendation applies to the current build only. Re-review the label before submission whenever analytics, crash reporting, accounts, cloud sync, advertising, remote APIs, or another third-party SDK is added.

## What the current app does

- Stores artwork archives and previews inside the app's local Application Support container.
- Processes strokes, colors, layers, masks, filters, animation frames, imported images, text, PSD files, GIFs, and time-lapse video on device.
- Opens files only after the user explicitly chooses them through Apple's document picker.
- Exports only after the user explicitly invokes Apple's share sheet. HueLoom itself does not upload exports to a developer-controlled server.
- Links only Apple system frameworks: UIKit, Foundation, CoreImage, ImageIO, UniformTypeIdentifiers, and AVFoundation.
- Bundles Masonry source for Auto Layout. Masonry contains no analytics, ads, account system, or networking component.

## What the current app does not do

- No account creation or authentication
- No developer-operated backend or network requests
- No advertising SDK
- No analytics or telemetry SDK
- No crash-reporting SDK
- No cross-app tracking or ATT prompt
- No collection of device identifiers
- No location, contacts, calendar, health, microphone, or camera access
- No direct Photos-library permission request; image import uses the system document picker
- No push notifications
- No cookies or web views

## User content and sharing

Artwork and imported content remain local until the user selects an export destination. A destination chosen in the system share sheet may be operated by Apple or another installed third-party app and is governed by that destination's privacy policy. HueLoom does not receive data back from those destinations.

## Permissions and privacy manifest

The current `Info.plist` has no privacy-sensitive Usage Description keys because the app does not call APIs requiring camera, microphone, location, contacts, or direct photo-library access. No `PrivacyInfo.xcprivacy` file is currently present. The reviewed app code and bundled Masonry source do not use an Apple required-reason API that needs to be declared based on the current implementation.

## Submission requirements

- Apple still requires a public Privacy Policy URL for App Store submission.
- Host one of the included policy HTML files and replace the support-email placeholder before publishing.
- If App Analytics is enabled in App Store Connect, Apple-collected analytics are handled by Apple; do not claim that HueLoom itself collects them unless the developer receives or combines identifiable data.
