# One Go BackLoad Android APK

This repository builds a Trusted Web Activity APK for the live One Go BackLoad app. The Android launcher icon is the supplied One Go Business Solutions logo at `android/icon/onego-business-solutions.png`.

## Build and download

1. Open the repository's **Actions** tab.
2. Select **Build OneGo BackLoad APK** and choose **Run workflow** (a change under `android/` also starts a build).
3. When the run finishes, download the **onego-backload-apk** artifact. It contains `app-release-signed.apk`.

The workflow produces a signed test APK with a temporary key when signing secrets are not configured. That APK is suitable for a first install, but a later APK signed with a different key cannot update it in place. For repeatable upgrades or Google Play release, save the signing keystore as repository Actions secrets named `ONEGO_KEYSTORE_BASE64`, `ONEGO_KEYSTORE_PASSWORD`, and (optionally) `ONEGO_KEY_PASSWORD`.

A Trusted Web Activity needs a Digital Asset Links file on the live site to open without Chrome's address bar and enable full TWA verification. The signing certificate must be added at `/.well-known/assetlinks.json` on the live OneGo domain before store release.
