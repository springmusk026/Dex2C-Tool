# Dex2C Tool

An Android application for converting DEX bytecode to native C/C++ code, providing binary-level protection against reverse engineering. Built on top of the [dex2c](https://github.com/codehasan/dex2c) and [dcc](https://github.com/amimo/dcc) open-source protection engines.

## Overview

Dex2C Tool runs the full DEX-to-native compilation pipeline on-device via an embedded Termux environment. No desktop toolchain is required — setup, compilation, and APK re-signing are handled automatically within the app.

## Features

- **DEX → Native compilation** — Converts selected methods to native C code compiled with the Android NDK.
- **APK browser** — Parses APK files and displays packages, classes, and methods in a navigable trie structure.
- **Filter rule builder** — Whitelist or blacklist specific classes and packages using pattern-based rules.
- **Advanced build options** — String obfuscation, dynamic JNI registration, synthetic method skipping, custom loaders, and project archives.
- **Resource monitor** — Real-time CPU, RAM, and disk usage during protection runs.
- **Protection history** — Persistent log of all prior protection runs with detailed output.
- **Theming** — Dark, light, and AMOLED modes with six accent colors. Preferences persist across sessions.
- **Remote configuration** — Feature flags, version management, announcements, maintenance mode, and in-app self-update, controlled via a hosted JSON configuration file.
- **In-app self-update** — Downloads and installs updates directly within the app with progress tracking.
- **Rate limiting** — Configurable daily operation limits controlled remotely.
- **Kill switch** — Remote version-level app disabling for deprecated releases.
- **Integrity protection** — Runtime signing certificate verification and obfuscated configuration URL to prevent tampering.

## Requirements

- Android 7.0 (API 24) or higher
- [Termux](https://github.com/termux/termux-app) installed from F-Droid
- Approximately 500 MB of storage for the toolchain (Python, NDK, dependencies)

## Installation

1. Install Termux from [F-Droid](https://f-droid.org/en/packages/com.termux/).
2. Launch Dex2C Tool and follow the setup flow. The app bootstraps the Termux environment, installs Python, the Android NDK, and all required dependencies automatically.
3. Once setup completes, the main protection screen is available.

No manual terminal commands are required.

## Usage

1. Navigate to the **Protect** screen.
2. Select an APK file.
3. Optionally configure filter rules to target specific classes or packages.
4. Optionally adjust advanced build options.
5. Tap **Protect APK** to begin the conversion.
6. Share or export the protected APK from the result card.

### Filter Rule Syntax

| Pattern | Description |
|---------|-------------|
| `com/example/app;.*` | Protect all methods in a class |
| `com/example/.*;.*` | Protect all classes in a package |
| `.*;onCreate\(.*` | Protect `onCreate` in every class |
| `!com/example/;.*` | Exclude a class from protection |

## Architecture

- **Language**: Kotlin
- **UI**: Jetpack Compose with Material 3
- **Dependency injection**: Hilt
- **Database**: Room
- **Navigation**: Navigation Compose
- **Preferences**: DataStore
- **Image loading**: Coil
- **JSON parsing**: Gson
- **APK analysis**: apk-parser

## Remote Configuration

The app fetches a JSON configuration file from a remote endpoint on each launch. This enables:

- Version checks and forced update enforcement
- Maintenance mode activation
- Feature flag toggling
- Announcement banners and launch sheets
- Device-level and version-level blocking
- Daily rate limiting for protection operations
- In-app changelog, tips, promo banners, feedback prompts, and surveys

See [`data.json`](data.json) for the configuration schema.

## Open Source Acknowledgements

This project depends on the following open-source libraries:

| Library | License |
|---------|---------|
| [dex2c](https://github.com/codehasan/dex2c) | Apache 2.0 |
| [dcc](https://github.com/amimo/dcc) | Apache 2.0 |
| [androguard](https://github.com/androguard/androguard) | Apache 2.0 |
| [Jetpack Compose](https://developer.android.com/jetpack/compose) | Apache 2.0 |
| [Hilt](https://dagger.dev/hilt/) | Apache 2.0 |
| [Room](https://developer.android.com/jetpack/androidx/releases/room) | Apache 2.0 |
| [Navigation Compose](https://developer.android.com/jetpack/compose/navigation) | Apache 2.0 |
| [DataStore](https://developer.android.com/topic/libraries/architecture/datastore) | Apache 2.0 |
| [Coil](https://coil-kt.github.io/coil/) | Apache 2.0 |
| [Gson](https://github.com/google/gson) | Apache 2.0 |
| [apk-parser](https://github.com/hsiafan/apk-parser) | BSD 2-Clause |
| [Kotlin](https://kotlinlang.org) | Apache 2.0 |
| [Kotlin Coroutines](https://github.com/Kotlin/kotlinx.coroutines) | Apache 2.0 |
| [Material Icons Extended](https://fonts.google.com/icons) | Apache 2.0 |

Full license details are available in the app under **Settings → Open Source Licenses**.

## Developer

| | |
|-|-|
| **GitHub** | [@springmusk026](https://github.com/springmusk026) |
| **Telegram** | [@springmusk](https://t.me/springmusk) |
| **Channel** | [@Layout_musk](https://t.me/Layout_musk) |

## License

```
Copyright 2026 Spring Musk

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
