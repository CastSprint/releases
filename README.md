# CastSprint Releases — Official Distribution Hub

Official public releases, verified installers, mobile APKs, and cryptographic SHA-256 checksums for the entire **CastSprint Creator Suite**, engineered by [TA Shanto](https://tashanto.com).

> **Automatic Website Sync:** Every GitHub Release published in this repository automatically syncs live to [castsprint.tashanto.com/download](https://castsprint.tashanto.com/download) and each individual product page!

---

## CastSprint Creator Suite Products

| Product | Description | Platforms | Tag Prefix | Source Repository |
| :--- | :--- | :--- | :--- | :--- |
| **CastSprint Screen** | Sub-15ms USB & Wi-Fi Mobile Screen Mirroring + OBS Capture | macOS, Windows, Linux, iOS, iPadOS, Android | `screen-v*` / `v0.*` | [CastSprint/castsprint-screen](https://github.com/CastSprint/castsprint-screen) |
| **CastSprint Camera** | 4K 60 FPS Pro Virtual Webcam (iPhone/iPad/Android → Desktop) | macOS, Windows, Linux, iOS, iPadOS, Android | `camera-v*` | [CastSprint/castsprint-camera](https://github.com/CastSprint/castsprint-camera) |
| **CastSprint Audio** | Native Studio Audio Mixer, Per-App Routing, 5-Band EQ & Phone Mic | macOS, Windows, Linux, iOS, iPadOS, Android | `audio-v*` | [CastSprint/castsprint-audio](https://github.com/CastSprint/castsprint-audio) |
| **CastSprint Live** | Mobile Gaming & IRL Live Streaming Studio (Direct Multi-RTMP, Overlays, °C Monitor) | iOS, iPadOS, Android Phone & Tablet | `live-v*` | [CastSprint/castsprint-live](https://github.com/CastSprint/castsprint-live) |

---

## Release Tag & Asset Naming Convention (For Automatic Website Sync)

The website (`src/lib/github-release.ts`) automatically classifies every release & asset into the right product page and platform card based on these exact naming conventions:

- **CastSprint Screen** (`tag: screen-v0.3.3` or `v0.3.3`):
  - `CastSprint-Screen-vX.Y.Z-macOS.dmg`
  - `CastSprint-Screen-vX.Y.Z-Windows-x64.zip`
  - `CastSprint-Screen-vX.Y.Z-Linux-x86_64.tar.gz`
  - `CastSprint-Screen-vX.Y.Z-Android.apk`
- **CastSprint Camera** (`tag: camera-v0.2.0`):
  - `CastSprint-Camera-vX.Y.Z-macOS.dmg`
  - `CastSprint-Camera-vX.Y.Z-Windows-x64.zip`
  - `CastSprint-Camera-vX.Y.Z-Linux-x86_64.tar.gz`
  - `CastSprint-Camera-vX.Y.Z-Android.apk`
- **CastSprint Audio** (`tag: audio-v0.1.0`):
  - `CastSprint-Audio-vX.Y.Z-macOS.dmg`
  - `CastSprint-Audio-vX.Y.Z-Windows-x64.zip`
  - `CastSprint-Audio-vX.Y.Z-Linux-x86_64.tar.gz`
  - `CastSprint-Audio-vX.Y.Z-Android.apk`
- **CastSprint Live** (`tag: live-v0.1.0`):
  - `CastSprint-Live-vX.Y.Z-Android.apk`
  - `CastSprint-Live-vX.Y.Z-iOS.ipa` (TestFlight / Signed Distribution)
- **Checksums (included in every release):** `SHA256SUMS`

---

## Publishing a New Release (Tag + Upload + Auto-Sync)

```bash
# 1. Generate SHA256SUMS for your release artifacts
shasum -a 256 dist-release/* > dist-release/SHA256SUMS

# 2. Tag and publish via GitHub CLI (example for CastSprint Live v0.1.0)
gh release create live-v0.1.0 dist-release/* \
  --repo CastSprint/releases \
  --title "CastSprint Live v0.1.0 — Mobile Gaming RTMP Studio" \
  --notes "Zero-heat native iOS/iPadOS & Android gaming live streaming studio with multi-RTMP/RTMPS, Image/GIF/Video/Web output overlays, broadcast scenes, dual audio mixer, and live Celsius (°C) thermal monitor."
```

## Verifying Downloads (SHA-256)

```bash
# macOS / Linux
shasum -a 256 -c SHA256SUMS

# Windows (PowerShell)
Get-FileHash .\CastSprint-Screen-v0.3.3-Windows-x64.zip -Algorithm SHA256
```
