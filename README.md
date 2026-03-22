# Dex2C Tool

> **Convert Android DEX bytecode to native C/C++ — protect your app's logic from reverse engineering.**

Dex2C Tool is a free Android application that lets you run the [dex2c](https://github.com/codehasan/dex2c) / [dcc](https://github.com/amimo/dcc) protection pipeline directly on your device via Termux — no PC required.

---

## ✨ Features

| Feature | Details |
|---------|---------|
| 🛡️ **DEX → Native** | Converts selected methods to native C code compiled via NDK |
| 📦 **APK Browser** | Parse any APK and visually browse packages & classes in a trie tree |
| 🎯 **Filter Builder** | Whitelist / blacklist specific classes and packages with a visual rule builder |
| ⚙️ **Advanced Options** | Obfuscation, dynamic registration, skip synthetics, custom loader, and more |
| 📊 **Resource Monitor** | Real-time CPU, RAM and disk usage bar during protection |
| 🕓 **History** | Full log-backed history of every protection run |
| 🎨 **Themes** | Dark · Light · AMOLED modes with 6 accent color options, persisted across restarts |
| 🔔 **Settings** | Privacy Policy, Terms of Service, OSS Licenses, Developer page — all built-in |

---

## 📲 Installation

1. Install [Termux](https://github.com/termux/termux-app) from F-Droid.
2. Run the **setup flow inside the app** — it bootstraps Termux, installs Python, NDK and all dependencies automatically.
3. Once setup completes, tap **Protect** and select your APK.

> No manual terminal commands needed. The app drives everything.

---

## 🚀 Usage

### Basic Protection

1. Tap **Protect** on the bottom nav.
2. Tap the APK card to pick your `.apk` file.
3. *(Optional)* Open **Filter Rules** → browse classes and add whitelist/blacklist rules.
4. *(Optional)* Expand **Advanced Options** to tune the build.
5. Tap **Protect APK**.
6. Share the output APK when done.

### Filter Rules Quick Reference

| Pattern | Effect |
|---------|--------|
| `com/example/app;.*` | Protect all methods in a class |
| `com/example/.*;.*` | Protect an entire package |
| `.*;onCreate\(.*` | Protect `onCreate` in every class |
| `!com/example/;.*` | Blacklist (exclude) a class |

---

## 🔒 About This Product

- **Free to use** — no subscription, no ads.
- **Source code is not public.** The app itself is a proprietary product; the underlying protection engines ([dex2c](https://github.com/codehasan/dex2c), [dcc](https://github.com/amimo/dcc), [androguard](https://github.com/androguard/androguard)) remain open-source and are credited accordingly.
- Do **not** redistribute, decompile, or modify the app binary.

---

## 🧩 Open Source Acknowledgements

This product is built on top of the following open-source projects:

- [dex2c](https://github.com/codehasan/dex2c) — GPL 2.0
- [dcc](https://github.com/amimo/dcc) — GPL 2.0
- [androguard](https://github.com/androguard/androguard) — Apache 2.0
- Jetpack Compose, Hilt, Room, Navigation, DataStore, apk-parser, Coil — Apache 2.0 / MIT

Full license text is available inside the app under **Settings → Open Source Licenses**.

---

## 👤 Developer

| | |
|-|-|
| **Name** | Spring Musk |
| **GitHub** | [@springmusk026](https://github.com/springmusk026) |
| **Telegram** | [@springmusk](https://t.me/springmusk) |
| **Channel** | [@Layout\_musk](https://t.me/Layout_musk) |

---

## 📄 Legal

By using this app you agree to the [Terms of Service](https://t.me/Layout_musk) included in the app.  
This app does not collect, transmit or share any personal data. See the in-app Privacy Policy for details.

---

<p align="center">Made with ❤️ · Free forever</p>
