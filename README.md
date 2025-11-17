# QR Code Hex Reader

[![GitHub Release](https://img.shields.io/github/v/release/kibotu/hexqr)](https://github.com/kibotu/hexqr/releases)

> **See what others hide.** The only QR code reader that shows you the actual bytes, not just the interpreted content. Essential for security professionals, developers, and anyone who values transparency.

![QR Code Reader Demo](docs/record.gif)

---

## Why This Exists

Every QR code reader tells you *what* it thinks the code contains. But what if you need to know *exactly* what's encoded? 

QR codes can hide tracking redirects, non-standard encodings, and unexpected data that standard parsers miss. This app gives you the transparency to see the raw bytes—the ground truth—so you can make informed decisions about what you're scanning.

**Built for those who believe in seeing the full picture.**

---

## What Makes This Different

### 🔍 **Raw Byte Transparency**
Unlike standard readers that only show interpreted content, we display the actual raw bytes. This isn't just a feature—it's the foundation of trust and security.

### 🛡️ **Security-First Design**
Detect tracking redirects before clicking. Verify URLs. Audit suspicious content. All without sending data anywhere—everything processes locally on your device.

### 🎯 **Smart Parsing, Full Control**
We intelligently parse common formats (URLs, contacts, WiFi, email, SMS, locations, calendar events) while always preserving access to the underlying raw data. Best of both worlds.

### ⚡ **Offline-First Architecture**
No network required. No data collection. No tracking. Your privacy isn't an afterthought—it's built into every design decision.

---

## Quick Start

### For Users

1. **Download** the latest APK from [GitHub Releases](https://github.com/kibotu/hexqr/releases)
2. **Install** on your Android device (6.0+)
3. **Grant** camera permission when prompted
4. **Scan** a QR code and tap "Hex Editor" to see the raw bytes

**System Requirements:** Android 6.0 (API 23) or higher, camera hardware

### For Developers

```bash
# Clone and build
git clone https://github.com/kibotu/hexqr.git
cd hexqr
./gradlew assembleDebug
```

See [Building](#building) for detailed setup instructions.

---

## Supported Formats

The app intelligently parses and displays:

- **URLs** — Protocol, domain, path, query parameters, fragments
- **Contacts (vCard)** — Name, phone, email, address, organization
- **WiFi Networks** — SSID, security type, password, hidden flag
- **Email** — Address, subject, body
- **SMS** — Phone number and message
- **Geographic Location** — Latitude, longitude, altitude
- **Calendar Events** — Title, dates, location, description
- **Plain Text** — Raw text with encoding information

All formats maintain full access to raw byte data through the hex editor.

---

## Privacy & Security

We take privacy seriously. Here's what that means in practice:

- ✅ **Zero network requests** — Everything processes offline
- ✅ **No data collection** — No analytics, no tracking, no telemetry
- ✅ **Local processing only** — Camera data never leaves your device
- ✅ **No automatic storage** — Content is only saved when you explicitly share it

Your data stays yours. Always.

---

## Building

### Prerequisites

- **Android Studio** — Hedgehog (2023.1.1) or later
- **JDK** — Version 21 or higher
- **Android SDK** — API 23+ (Android 6.0)
- **Gradle** — Included via wrapper

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/kibotu/hexqr.git
   cd hexqr
   ```

2. **Configure signing** (for release builds)
   ```bash
   cp keystore.properties.example keystore.properties
   # Edit keystore.properties with your release keystore credentials
   ```

3. **Open in Android Studio**
   - Select "Open an Existing Project"
   - Navigate to the cloned directory
   - Wait for Gradle sync to complete

4. **Build**
   ```bash
   # Debug build
   ./gradlew assembleDebug
   
   # Release build (requires keystore.properties)
   ./gradlew assembleRelease
   ```

   APK files are generated in `app/build/outputs/apk/`

### Troubleshooting

- **Camera issues:** Ensure permission is granted and no other app is using the camera
- **QR not detected:** Check lighting, hold steady, keep code in frame
- **Build failures:** Verify JDK 21 is installed, sync Gradle, clean build: `./gradlew clean build`

---

## Technical Details

**Architecture:** MVVM with StateFlow  
**Language:** Kotlin 2.2.21  
**UI Framework:** Jetpack Compose (BOM 2025.11.00)  
**Camera:** CameraX + ML Kit Barcode Scanning  
**Dependency Injection:** Hilt  
**Minimum SDK:** API 23 (Android 6.0)  
**Target SDK:** API 36 (Android 15)

Built with modern Android best practices, focusing on maintainability, performance, and user experience.

---

## Contributing

We welcome contributions! Whether it's fixing bugs, adding features, or improving documentation, your help makes this project better.

**How to contribute:**
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

For major changes, please open an issue first to discuss your ideas. We're always happy to collaborate.

---

## Acknowledgments

Built with excellent open-source tools:

- [Jetpack Compose](https://developer.android.com/jetpack/compose) — Modern declarative UI
- [CameraX](https://developer.android.com/training/camerax) — Camera abstraction layer
- [ML Kit](https://developers.google.com/ml-kit) — Barcode scanning
- [Hilt](https://developer.android.com/training/dependency-injection/hilt-android) — Dependency injection

Thank you to the Android developer community for these incredible tools.

---

**Simple. Transparent. Privacy-focused.** That's the goal, and we're working to make it better every day.
