<div align="center">

# SuperFire TV

**Live TV, movies and series. One native Android experience.**

[Download the latest APK](https://github.com/daraptoor/SuperFireTV-source-updates/releases/latest) · [Release history](https://github.com/daraptoor/SuperFireTV-source-updates/releases) · [Report an issue](https://github.com/daraptoor/SuperFireTV-source-updates/issues)

Android phones · Tablets · Android TV · Android-based Fire TV

</div>

## A clearer way to watch

SuperFire TV brings live channels, movie and series catalogs, favorites, downloads and viewing progress into one app. Its Liquid Glass interface uses dark ambient backgrounds, rounded translucent controls and warm amber accents on phones and tablets, with dedicated remote navigation on TV.

This repository hosts public APK releases, update manifests and signed source configuration updates. The application code is maintained separately.

## What's new in 0.6.4

- **Liquid Glass design:** floating navigation, compact search, grouped settings, title details and playback sheets based on the all-screens design mockup.
- **Broader movie audio support:** bundled software decoding for Dolby Digital/Plus, DTS and TrueHD, with clearer audio track labels and fallback when a track cannot play.
- **Refined touch playback:** grouped player actions, a compact transport bar, brightness and volume gestures, and saved aspect-ratio preferences.
- **Animated home-screen widget:** adjustable appearance, size, glow and animation.

[Explore the design reference](docs/liquid-glass-all-screens.html) — an HTML mockup, not a device screenshot. Download the file and open it in a browser to view all screens. Android renders the glass appearance with lightweight gradients and borders; it does not use live background blur.

## Features

| Browse | Watch | Keep |
| --- | --- | --- |
| Live TV with channel groups and search | HLS, DASH and direct video playback | Favorites for channels, movies and series |
| Combined movie and series catalogs | Audio/subtitles, playback quality and speed | Continue Watching with resume positions |
| Custom M3U playlists and HTTPS streaming add-ons | Next episode and automatic stream fallback | Quality selection for supported downloads |
| Phone, tablet and TV layouts | Touch controls and TV remote navigation | Offline playback of completed downloads |

Catalogs and stream availability depend on third-party sources. Quality labels may be provider-reported. Use only content and sources you are authorized to access.

## Install

1. Open [Latest release](https://github.com/daraptoor/SuperFireTV-source-updates/releases/latest).
2. Download the **SuperFireTV-v…apk** asset. The other files support updates and audio-library rebuilding.
3. Open the APK on your Android device. If prompted, allow app installation for the browser or file manager you used.
4. Complete Android's installation prompt and launch **SuperFire TV**.

For Android TV or Android-based Fire TV, transfer the APK to the device and open it with a file manager, or use ADB:

```sh
adb install -r SuperFireTV-v0.6.4.apk
```

### Requirements

- Android 6.0 / API 23 or later; Android-based Fire OS 6 or later.
- ARMv7, ARM64, x86 or x86-64. One universal APK includes all four architectures.
- Internet access for browsing remote catalogs and streaming; completed downloads can play offline.
- No Google Play Services or SuperFire TV account required.

Fire OS 5 and devices that do not run Android are unsupported. Stream codecs, resolution and performance depend on the device. Software multichannel audio is decoded to PCM; Atmos bitstream passthrough is not provided.

## Get started

- **Live TV:** browse the saved Indian channel list or add your own playlist in Settings.
- **Movies / Series:** browse the combined catalog, search for a title, then choose a stream or episode.
- **Favorites / Continue:** save titles and resume previous viewing.
- **Downloads:** choose an available quality and manage supported offline downloads.
- **Settings:** manage sources, playback quality, layout, widget appearance and app updates.

## Updates

Use **Settings → App update** to check manually. Supported versions also check when the home screen opens. The download can continue in the background; return to the app to complete Android's installation prompt.

Before installation, the updater checks the download hash, package name, version code and signing certificate. An update must use the same signing certificate as the installed app. Do not uninstall merely to update: doing so removes local app data. If Android reports a signature conflict, check where your installed copy came from.

| File | Purpose |
| --- | --- |
| `SuperFireTV-v…apk` | Installable Android application |
| `update.json` | Version, APK download URL, SHA-256 and update notes |
| `SuperFireTV-v…-audio-source.tar.gz` | Corresponding FFmpeg/Media3 audio source, licenses and rebuild/replacement tools |
| `moviebox.json` | Signed, data-only provider configuration feed |

The provider feed can update connection metadata. Native features and interface changes require a new APK. The app does not silently install updates or execute code from that feed.

## Integrity and open-source notices

Each release's `update.json` records its APK SHA-256. You can compare it locally:

```sh
shasum -a 256 SuperFireTV-v0.6.4.apk
```

Audio decoding uses FFmpeg under LGPL-2.1-or-later and the AndroidX Media3 adapter under Apache-2.0. Matching audio sources and instructions for rebuilding and replacing the shared library are included with the release. Further attribution is available in **Settings → About & licenses**.

## Support

[Open an issue](https://github.com/daraptoor/SuperFireTV-source-updates/issues) with your app version, device model, Android/Fire OS version, the affected screen and steps to reproduce. Include the selected source and whether the problem affects one title or several. Remove private playlist URLs, credentials and personal information from screenshots and logs.

Build, unit-test and lint results are recorded in individual release notes. Hardware and provider availability are not guaranteed by those checks.
