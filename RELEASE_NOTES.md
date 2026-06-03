# Release Notes

## v1.6.0 — Hotspot Without Internet & Connection Modes

**Release Date:** June 3, 2026

- **Hotspot Without Internet** — A new "Hotspot with loopback interface" mode runs Windows Mobile Hotspot off a virtual loopback adapter, so your PC can broadcast a hotspot even when it has no internet connection. Ideal for in-car Tesla setups and other offline scenarios.
- **Connection Mode Selector** — Replaces the previous loopback toggle with a clear three-way choice — *Same network*, *Hotspot with internet*, *Hotspot with loopback* — selectable from a dedicated settings dialog with inline descriptions of each mode.
- **Getting Started Tutorial** — A new in-app tutorial walks new users through their first connection. Auto-shown on first launch, with device-first branching (Tesla vs. laptop/tablet) that maps to the appropriate connection mode. Reopen anytime from Help → Getting Started.
- **Release Notes on Update** — After an update, SideDisplay surfaces the cumulative changes since your previous version on first launch. Help → Release Notes opens the full history at any time. The update prompt also now displays full cumulative release notes instead of just the latest version's summary.
- **DHCP Reliability Overhaul** — Fixed four root causes that previously left clients stuck in DHCP INIT after an update: cleaner block-to-bind handoff, loopback-adapter lease filtering, directed subnet broadcasts so OFFER/ACK reach the right interface, and explicit handling of DECLINE/RELEASE/INFORM messages.
- **Stability & Polish** — PIN is now verified before display selection so a wrong PIN no longer strands the UI; offline diagnostic reports are queued and retried automatically on next launch; the connection mode dialog widens with a secondary Wi-Fi adapter option; settings dialog matches the rest of the dark theme.

---

## v1.5.0 — Encoder Selection & Performance

**Release Date:** April 25, 2026

- **Per-Display Encoder Selection** — Choose the H.264 hardware encoder (Intel QSV, NVIDIA NVENC, AMD AMF) or software fallback for each display from a new dropdown in display settings. "Auto" distributes available encoders across connected displays. Multiple displays can share the same encoder when needed.
- **Improved Video Performance** — GPU-accelerated BGRA→NV12 conversion with cursor rendering moves work off the CPU, reducing per-frame capture time by 40–60% on hybrid laptops.
- **Connection Stability** — Clients now receive a proper keyframe when the virtual display restarts (e.g. resolution change), eliminating frozen-video symptoms. AMF streams inject SPS/PPS on every IDR so WebRTC decoders can recover cleanly from packet loss.
- **Network Fixes** — DHCP server sends NAK on IP conflicts so clients re-acquire the correct address instead of hanging.
- **Stability** — Fixed AV crash on stop, eliminated ghost VDD devices left behind after unclean shutdown, and removed frame-drop artifacts during encoder switches.
- **Diagnostics** — Startup diagnostic snapshot now includes DXGI adapter vendor IDs and dedicated VRAM, helping troubleshoot hybrid laptop display issues.

---

## v1.4.4 — Connection Reliability

**Release Date:** April 15, 2026

- **More Reliable Connections** — Improved network stability so devices connect consistently and keep the same address across reconnects, even when Windows Internet Connection Sharing is enabled.

---

## v1.4.2 — Fallback Mode Fix

**Release Date:** April 13, 2026

- **Fallback Mode Fix** — Fixed network configuration getting stuck in fallback mode when the Wi-Fi Direct adapter description is non-standard (e.g. Realtek drivers). `NetworkConfigurator` now uses the same ICS IP-based fallback as hotspot detection, so the adapter is found and the IP change + DHCP server start correctly.

---

## v1.4.1 — Hotspot Detection Fix

**Release Date:** April 13, 2026

- **Hotspot Detection Fallback** — Fixed hotspot not being detected on systems where the Wi-Fi Direct adapter uses non-standard driver descriptions (e.g. Realtek). Added ICS IP-based fallback detection.

---

## v1.4.0 — Multi-Display & Stability

**Release Date:** April 9, 2026

- **Multi-Display Support** — Connect up to 3 devices simultaneously, each with independent virtual display and resolution settings.
- **Per-Display Settings** — Configure resolution and DPI scaling individually for each display via popover UI.
- **License Window Improvements** — Redesigned layout with email display, subscription status, and My Orders link.
- **Trial Timer Fix** — Timer now correctly pauses when browser disconnects or refreshes, and resumes on reconnect.
- **Improved Diagnostics** — Debug log resets on app start, diagnostic report window now shows reliably after stop.
- **Stability Improvements** — Graceful port conflict handling, fixed popup positioning, and improved VDD creation for custom resolutions.

---

## v1.3.0 — Diagnostics & Connection Improvement

**Release Date:** March 24, 2026

- **Faster Connection** — Improved signaling speed for quicker WebRTC connection setup.
- **Diagnostics** — New "Enable Diagnostics" option that logs detailed debug information including network interface state, firewall rules, and connection events. Diagnostic report can be submitted directly from the app after stopping.

---

## v1.2.0 — Improved Device Compatibility

**Release Date:** March 13, 2026

- **Better Captive Portal Handling** — Apple devices no longer show captive portal popups when internet access is disabled.

---

## v1.1.0

**Release Date:** March 8, 2026

### New Features
- **Internet Access Control** — Control whether connected devices can access the internet through your hotspot. Disabled by default to save hotspot data.
- **Always-on Domain Access** — The `go.ss` shortcut domain is now always active when hotspot is configured. No need to toggle it on manually.

---

## v1.0.6 — Clean Browser Display

**Release Date:** March 3, 2026

- Removed debug overlay and latency display from browser client

---

## v1.0.5 — Adapter IP Restore Fix

**Release Date:** March 3, 2026

- Fixed adapter IP not being restored to original value on cleanup

---

## v1.0.4 — Improved Connection Stability

**Release Date:** March 3, 2026

- Improved connection stability

---

## v1.0.3 — Signed Virtual Display Driver

**Release Date:** March 2, 2026

- Use signed Virtual Display Driver

---

## v1.0.0 — First Stable Release

**Release Date:** March 2, 2026

- First stable version of SideDisplay for Windows

---

## v0.9.5 — Bug Fixes

**Release Date:** March 2, 2026

- Fixed minor bugs and improved stability

---

## v0.9.4 — Bug Fixes

**Release Date:** March 2, 2026

- Fixed minor bugs and improved stability

---

## v0.9.3 — Bug Fixes

**Release Date:** March 2, 2026

- Fixed minor bugs and improved stability

---

## v0.9.0 — Initial Release

**Release Date:** March 2, 2026

SideDisplay for Windows is now available. This is the first official release.

### Features

- Display your Android device screen on your Windows PC as a side monitor
- Low-latency screen mirroring via USB/Wi-Fi connection
- Lightweight and easy to set up

### System Requirements

- Windows 10 or later (64-bit)

### Installation

Download the installer from the [Releases](https://github.com/AirOnSkin/SideDisplayWindows/releases) page.
