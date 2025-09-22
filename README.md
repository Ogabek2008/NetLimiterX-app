# NetLimiterX
A tool to control bandwith of hosts in your network.

## Overview

NetLimiterX is a lightweight Windows utility and UI to monitor, limit, and block network bandwidth per device on your local network. It provides a clean interface and a simple installer so you can get started quickly.

## How it works

NetLimiterX combines device discovery and low‑level packet filtering to control traffic:

1. **Device discovery**
   - The app scans your local network to find active devices (IP/MAC, hostname, vendor).
   - Discovered devices are listed in the UI where you can select targets for limiting or blocking.

2. **Traffic control**
   - Under the hood, NetLimiterX uses a packet capture/diversion driver (WinDivert) to intercept and manage traffic.
   - **Limiting**: packets for selected devices are queued and rate‑limited to the configured download/upload caps.
   - **Blocking**: traffic can be dropped entirely for a device (temporary block/unblock).
   - **Forwarding/filters**: rules are applied dynamically from the UI and take effect immediately.

3. **Safe by design**
   - Rules are scoped to your selected devices and can be removed at any time.
   - No permanent system changes beyond loading the driver while the app is active.

## Features

- Per‑device bandwidth limiting (download/upload)
- One‑click block / unblock
- Device scanner with IP/MAC info
- Clean, minimal UI for Windows 10/11

## Dependencies

Runtime (end users):
- Windows 10 or Windows 11, 64‑bit
- WinDivert kernel driver (the application loads the required driver files during operation)

Build/tooling (contributors):
- .NET SDK 8.0+
- Node.js 18+ (for the website in `NetLimiterX/`)
- Inno Setup (to build the Windows installer from `installer.iss`)
- WinDivert SDK files (included in the repository under `EvilLimiter.UI/Native/WinDivert/` for development)

## Installation

1. Download the latest installer:
2. Run `NetLimiterX_Setup_*.exe`.
3. Follow the setup wizard (Windows may ask for administrator approval to install the driver).
4. Launch NetLimiterX from the Start Menu or desktop shortcut.

## Usage

1. Open NetLimiterX.
2. Click **Scan** to discover devices on your local network.
3. Select a device and set **Download** / **Upload** limits (e.g., 2 Mbps) or choose **Block**.
4. Apply changes. Rules take effect immediately.
5. Remove or adjust rules at any time.

## System Requirements

- Windows 10/11 (64‑bit)
- 4 GB RAM (8 GB recommended)
- ~200 MB free disk space

## Founder

Created and maintained by **Ogabek** (GitHub: [@Ogabek2008](https://github.com/Ogabek2008)).

## Contributing

Contributions are welcome. Please open an issue to discuss a feature or bugfix before submitting a PR.

## License

This project is licensed under the MIT License.
