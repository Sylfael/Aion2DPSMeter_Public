# Aion2DPSMeter (beta releases)

Aion2DPSMeter is a damage meter for **AION 2** on Windows. It reads the game's network traffic on your own PC (with Npcap) and shows your party's damage in a small overlay. There is also a fight details window (skills, buffs, damage taken, recent fights) and an inspector for party applicants and members.

This repository only holds the **release files** and the update manifest (`latest.json`). The source code is private.

> **Beta.** A handful of testers use it, and the numbers can be wrong, especially after a game patch. Then the overlay shows an amber "unverified protocol" warning.
> It is an unofficial fan tool, not affiliated with or endorsed by NCSOFT. Third-party tools may be against the game's terms of service. Use it at your own risk.

## Requirements

- Windows 10 or 11 (64-bit).
- [Npcap](https://npcap.com/) (Wireshark installs it too).
- WebView2, which is built into Windows 10/11.

## Install

1. Download the newest kit from [`releases/`](releases/). The current one is listed in [`latest.json`](latest.json).
2. Optional: check the download in PowerShell with `Get-FileHash .\Aion2DPSMeter-kit-<version>.zip`. The hash must match `SHA256SUMS` in the same folder and `sha256` in `latest.json`.
3. Unzip it to a folder you can write to, such as your Documents or Desktop. Do not use `Program Files`: updates replace files in this folder. Keep the layout (`app\`, `recorder\`, `probe\`).
4. Start `app\aion2dpsmeter.exe`. The builds are not code-signed yet, so Windows may say "Windows protected your PC". Choose **More info → Run anyway**.
5. `START-HERE.md` in the kit has the rest: the tray icon, the click-through hotkey (Ctrl+Shift+M), and the recorder for test sessions.

Testers with an old kit (kit 1 to 7, shown as version 0.0.1) install 0.7.0 by hand once. From 0.7.0 on, the meter updates itself when you click.

## How updates work

- About 30 seconds after the meter starts, and then every 6 hours, it reads [`latest.json`](latest.json) from this repository. You can turn this off in ⚙ with "Check for updates".
- When a newer version exists, ⚙ shows a small dot and the release notes. **Nothing installs without your click.**
- **Update now** downloads the kit from this repository only and checks its size and SHA-256 against `latest.json`. It then replaces the files and restarts the meter. The previous version stays next to it as `app\aion2dpsmeter.prev.exe`, and ⚙ "Roll back" returns to it. If any step fails, the files are put back. Every step is written to `%LOCALAPPDATA%\Aion2DPSMeter\logs\meter.log`.
- The meter only fetches from `raw.githubusercontent.com`, `github.com` and `objects.githubusercontent.com`, and only from this repository. These addresses are fixed in the program.

> **Beta updates are not signed yet.** The checks above catch a damaged or redirected download, but not a bad release published here. **Only run builds published by the owner of this repository**, and do not run copies from anywhere else. Signed releases are planned: the meter will then refuse any update without the owner's signature.

## Privacy

See [PRIVACY.md](PRIVACY.md) for what the meter sends and what it never sends. In short: there is no telemetry, and your fights stay on your PC.

## Feedback

Testers send feedback to the owner directly: screenshots, the recorder zip from test sessions, and `meter.log` when something misbehaves.
