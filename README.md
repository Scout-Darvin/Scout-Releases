# 🦅 Scout — Official Releases & Distribution Hub

[![Release](https://img.shields.io/github/v/release/Scout-Darvin/Scout-Releases?color=f97316&label=Latest%20Release&style=flat-square)](https://github.com/Scout-Darvin/Scout-Releases/releases/latest)
[![Platform: Windows](https://img.shields.io/badge/Platform-Windows%20x64-0078D6?logo=windows&logoColor=white&style=flat-square)](https://github.com/Scout-Darvin/Scout-Releases/releases/latest)
[![Platform: macOS](https://img.shields.io/badge/Platform-macOS%20Universal-000000?logo=apple&logoColor=white&style=flat-square)](https://github.com/Scout-Darvin/Scout-Releases/releases/latest)
[![Platform: Linux](https://img.shields.io/badge/Platform-Linux%20x64-FCC624?logo=linux&logoColor=black&style=flat-square)](https://github.com/Scout-Darvin/Scout-Releases/releases/latest)
[![License](https://img.shields.io/badge/License-Proprietary-gray?style=flat-square)](https://github.com/Scout-Darvin/Scout-Releases)
[![Engine](https://img.shields.io/badge/Engine-Tauri%202.0%20%7C%20Rust-brightgreen?style=flat-square)](https://tauri.app)

Welcome to the official binaries and release distribution repository for **Scout**, the offline-first, privacy-engineered AI meeting assistant and intelligence workstation.

This repository hosts official production installers (`.exe`, `.msi`, `.dmg`, `.AppImage`), delta auto-update bundles (`.nsis.zip`, `.tar.gz`), cryptographic signatures (`.sig`), and the live `latest.json` auto-update manifest.

---

## 📥 Official Download Matrix

| Platform | Architecture | Installer Type | Direct Download Link | Format |
| :--- | :--- | :--- | :--- | :--- |
| **Windows 10 / 11** | `x64` (64-bit) | Standard Setup Installer | [Scout_x64-setup.exe](https://github.com/Scout-Darvin/Scout-Releases/releases/latest/download/Scout_0.2.0_x64-setup.exe) | NSIS Executable |
| **Windows 10 / 11** | `x64` (Enterprise) | MSI Package | [Scout_x64_en-US.msi](https://github.com/Scout-Darvin/Scout-Releases/releases/latest/download/Scout_0.2.0_x64_en-US.msi) | Windows Installer |
| **macOS** | `Universal` (Apple Silicon & Intel) | DMG Disk Image | [Scout_universal.dmg](https://github.com/Scout-Darvin/Scout-Releases/releases/latest/download/Scout_0.2.0_universal.dmg) | Apple Disk Image |
| **macOS** | `Universal` (Apple Silicon & Intel) | Compressed App Bundle | [Scout_universal.app.tar.gz](https://github.com/Scout-Darvin/Scout-Releases/releases/latest/download/Scout_0.2.0_universal.app.tar.gz) | Tarball Archive |
| **Linux** | `x86_64` | Portable AppImage | [Scout_amd64.AppImage](https://github.com/Scout-Darvin/Scout-Releases/releases/latest/download/Scout_0.2.0_amd64.AppImage) | Executable AppImage |
| **Linux** | `x86_64` (Debian/Ubuntu) | Debian Package | [Scout_amd64.deb](https://github.com/Scout-Darvin/Scout-Releases/releases/latest/download/Scout_0.2.0_amd64.deb) | Deb Archive |

> **Note:** For past version downloads and full changelogs, explore all published releases in the [GitHub Releases Archive](https://github.com/Scout-Darvin/Scout-Releases/releases).

---

## 💻 System Requirements

### Windows
- **Operating System**: Windows 10 (Build 1903+) or Windows 11 64-bit
- **Architecture**: `x86_64` (Intel / AMD)
- **Runtime**: Microsoft Edge WebView2 Evergreen Runtime *(Preinstalled on modern Windows 10 & 11)*
- **Memory (RAM)**: Minimum 8 GB *(16 GB recommended for running on-device 7B LLMs and Whisper Large)*
- **Storage**: Minimum 2 GB free space (additional space required if downloading local AI model weights)

### macOS
- **Operating System**: macOS 12 (Monterey) or later
- **Architecture**: Apple Silicon (`arm64`: M1, M2, M3, M4) or Intel Core (`x86_64`)
- **Memory (RAM)**: Minimum 8 GB Unified Memory
- **Storage**: 2 GB free disk space

### Linux
- **Operating System**: Ubuntu 22.04 LTS+, Fedora 38+, Arch Linux, or glibc 2.31+ equivalent
- **Dependencies**: `webkit2gtk-4.1`, `libssl3`, `libayatana-appindicator3`
- **Memory (RAM)**: Minimum 8 GB

---

## 🔒 Cryptographic Verification

All Scout production binaries and update archives are signed using **Minisign** to guarantee authenticity, source verification, and binary tamper-proofing.

### Official Public Signing Key
```
dW50cnVzdGVkIGNvbW1lbnQ6IG1pbmlzaWduIHB1YmxpYyBrZXk6IEVDQTYzMUQ3ODc5N0M4MkEKUldRcXlKZUgxekdtN09DRkVWSHNpZlJseEVOUmpNd1dDSTNaLzZ3MXJGTnY3WW1pdnlOYjBpbkIK
```

### Verifying SHA-256 Checksums

#### Windows (PowerShell):
```powershell
Get-FileHash -Algorithm SHA256 .\Scout_0.2.0_x64-setup.exe
```

#### macOS & Linux (Terminal):
```bash
shasum -a 256 Scout_0.2.0_universal.dmg
```

Compare the output hash against the `SHA256SUMS.txt` published with each release.

---

## ⚡ Built-in Auto-Update System

Scout includes an automated, cryptographically verified updater powered by Tauri 2.0.

- **Manifest Endpoint**:
  ```
  https://github.com/Scout-Darvin/Scout-Releases/releases/latest/download/latest.json
  ```
- **Differential NSIS Updates**: Windows builds download lightweight delta bundles (`.nsis.zip`) instead of re-downloading the complete installer.
- **Security & Integrity Policy**:
  - Scout automatically queries the release manifest on launch and periodically in the background.
  - When a new version is published with critical patches or new capabilities, Scout prompts for immediate seamless update.
  - Scout features an offline grace period: if the app is disconnected from update servers for more than 5 consecutive days, it prompts the user to verify internet connectivity to ensure essential security patches are maintained.

---

## 🚀 Release Channels

| Channel | Description | Cadence |
| :--- | :--- | :--- |
| **Stable (`latest`)** | Production-ready builds tested for maximum stability, privacy, and performance. | Bi-weekly / Monthly |
| **Beta / Preview** | Early-access builds featuring experimental features and engine upgrades. | Weekly |

---

## 📄 License & Legal

© 2026 Scout AI & Darvin Technologies. All rights reserved.  
The Scout software binary and its associated assets are distributed under the Scout Proprietary Software License.
