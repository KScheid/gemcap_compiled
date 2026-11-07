<img src="https://github.com/user-attachments/assets/25d71cea-101a-4813-b54d-8ae8259ff2e4" width="386" alt="gemcap logo">

# Gemcap (auto-compiled fork)

An Android browser for the Gemini protocol, built with Kotlin.

> **This is a fork of [hugmouse/gemcap](https://github.com/hugmouse/gemcap) that builds a ready-to-install APK.**
> The upstream project doesn't publish APKs, so a GitHub Action here builds the latest upstream code and posts it to [Releases](https://github.com/KScheid/gemcap_compiled/releases). All credit for the app goes to the original developer.

## Install

### With Obtainium (recommended — gets updates automatically)

[<img src="https://raw.githubusercontent.com/ImranR98/Obtainium/main/assets/graphics/badge_obtainium.png" alt="Get it on Obtainium" height="60">](https://apps.obtainium.imranr.dev/redirect?r=obtainium://add/https://github.com/KScheid/gemcap_compiled)

Tap the badge on your Android phone with [Obtainium](https://github.com/ImranR98/Obtainium) installed.
If the link doesn't open, add the app manually in Obtainium with this URL:

```
https://github.com/KScheid/gemcap_compiled
```

### Manual download

Grab the `.apk` from the [latest release](https://github.com/KScheid/gemcap_compiled/releases/latest) and install it.

- Requires Android 10 or newer.
- This build is **not** signed with the developer's key, so it can't update a copy installed from Google Play. Uninstall that one first.

## How the builds work

- The [Build & Release APK](.github/workflows/build-release.yml) workflow checks upstream once a day.
- If upstream has new commits, it builds a release APK, signs it, and publishes a new release.
- If nothing changed, it skips — no duplicate releases.
- Version numbers are upstream's version plus the build number (e.g. `11.0.3`), so every build counts as an update.
- To build right now: **Actions → Build & Release APK → Run workflow** (tick *force* to rebuild even if upstream is unchanged).

### Signing key

- By default, APKs are signed with `signing/fallback.jks`. Its password is public (it's in the workflow), so it only keeps updates consistent — it isn't a secret.
- To sign with a private key instead, add these repo secrets (**Settings → Secrets and variables → Actions**):
  - `KEYSTORE_BASE64` — the keystore file, base64-encoded
  - `KEYSTORE_PASSWORD`
  - `KEY_ALIAS`
  - `KEY_PASSWORD` — optional, defaults to `KEYSTORE_PASSWORD`
- Switching keys changes the app's signature, so you'll need to uninstall and reinstall once.

---

*Original upstream README below.*

## Join the closed testing

Join the Google Group to get access to official builds on Google Play!

- Join the group
- Click on a special link on "*Join the Gemcap testing on Android!*"
- Download the build from Google Play!

https://groups.google.com/u/0/g/gemcap-testing/c/80RyebVFEXg

## Screenshots

On mobile:

<p align="center">
  <img src="https://github.com/user-attachments/assets/e0ef44bc-4cf2-4513-952f-705b1427ea24" width="200" alt="screenshot on a phone #1" />
  <img src="https://github.com/user-attachments/assets/4c55a1e6-7ff9-4b99-a867-d4c4edd76bd7" width="200" alt="screenshot on a phone #2" />
  <img src="https://github.com/user-attachments/assets/b6b981f9-735f-4be0-8188-c80e65d60371" width="200" alt="screenshot on a phone #3" />
  <img src="https://github.com/user-attachments/assets/bfe70cfb-ba78-44fd-9f98-e96c291c0c6a" width="200" alt="screenshot on a phone #4" />
</p>

On foldables and tablets:

<p align="center">
  <img width="350" alt="screenshot on foldable phone" src="https://github.com/user-attachments/assets/e140ff2f-3343-4cd4-a9f5-ed7bf523382a" />
  <img width="466" alt="screenshot on a tablet" src="https://github.com/user-attachments/assets/4c0bff79-a74e-4e80-b062-5d915584cc9a" />
</p>

## Getting Started

### Prerequisites

- Android Studio 2025.2.3 (so you have the same bugs as me)
- Android SDK API Level 30+ (android 10+)

### Building the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/hugmouse/gemcap.git
   ```
2. Open the project in Android Studio.
3. Sync Gradle files.
4. Run the app!

## License

This project is licensed under the Apache 2.0 - see the [LICENSE](LICENSE) file for details.
