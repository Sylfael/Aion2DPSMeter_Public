# Aion2DPSMeter (beta releases)

Aion2DPSMeter is a damage meter for **AION 2** on Windows. It reads the game's network traffic on your own PC (with Npcap) and shows your party's damage in a small overlay. There is also a fight details window (skills, buffs, damage taken, recent fights), an inspector for party applicants and members, and windows for field bosses, tickets, pets, gear and personal records.

This repository only holds the **release files** and the update manifest (`latest.json`). The source code is private.

> **Beta.** A handful of testers use it, and the numbers can be wrong, especially after a game patch. When the meter notices, the overlay shows an amber or red warning line.
> It is an unofficial fan tool, not affiliated with or endorsed by NCSOFT. Third-party tools may be against the game's terms of service. Use it at your own risk.
> It is a private build shared with friends, not for redistribution: see `NOTICE.txt` in the kit. The licences of the libraries and data it uses are in `THIRD-PARTY-NOTICES.txt` in the kit.

## Requirements

- Windows 10 or 11 (64-bit).
- [Npcap](https://npcap.com/) (Wireshark installs it too).
- WebView2, which is built into Windows 11 and current Windows 10.

## Install

1. Download the newest kit from [`releases/`](releases/). The current one is listed in [`latest.json`](latest.json).
2. Optional: check the download in PowerShell with `Get-FileHash .\Aion2DPSMeter-kit-<version>.zip`. The hash must match `SHA256SUMS` in the same folder and `sha256` in `latest.json`.
3. Unzip it to a folder you can write to, such as your Documents or Desktop. Do not use `Program Files`: updates replace files in this folder. Keep the layout (`app\`, `recorder\`, `probe\`) and keep `WebView2Loader.dll` next to the exe.
4. Start `app\aion2dpsmeter.exe`. The builds are not code-signed yet, so Windows may say "Windows protected your PC". Choose **More info → Run anyway**.
5. `START-HERE.md` in the kit has the rest: the tray icon, the click-through hotkey (Ctrl+Shift+M), and the recorder, which is only for test sessions the owner asks for.

Only one meter runs at a time. Starting it again while it runs (it may be hidden in the tray) brings the running meter's overlay back instead.

## How updates work

- **5 seconds after the meter starts**, and then every 6 hours while it runs, it reads [`latest.json`](latest.json) from this repository. You can turn this off in ⚙ with "Check for updates".
- When a newer version exists, the overlay and the tray say so, and Settings → About shows the release notes. **Nothing installs without your click.**
- **Update now** downloads the kit from this repository only and checks its size and SHA-256 against `latest.json`. It then replaces the files and restarts the meter. The previous version stays next to it as `app\aion2dpsmeter.prev.exe`, and ⚙ "Roll back" returns to it. If any step fails, the files are put back. Every step is written to `%LOCALAPPDATA%\Aion2DPSMeter\logs\meter.log`.
- From 0.21.0, after an update the old version waits for the new one to finish starting (up to 90 seconds). If the new one closes or does not finish starting, the files are put back, the old version starts again, and a message says so. That version is then not offered again; a newer one will be. (The update from 0.20.0 to 0.21.0 itself is not protected this way: 0.20.0 does not have it yet.)
- The meter only fetches from `raw.githubusercontent.com`, `github.com` and `objects.githubusercontent.com`, and only from this repository. These addresses are fixed in the program.

> **Beta updates are not signed yet.** The checks above catch a damaged or redirected download, but not a bad release published here. **Only run builds published by the owner of this repository**, and do not run copies from anywhere else. Signed releases are planned: the meter will then refuse any update without the owner's signature.

## If the meter will not start

1. Look for it in the tray first: it may already be running, hidden. Only one meter runs at a time.
2. After an update: start `app\aion2dpsmeter.prev.exe` (the previous version). In ⚙ → About, **Roll back** makes it the main version again.
3. If that does not start either, go back by hand: quit every `aion2dpsmeter.exe` in Task Manager, then in the `app` folder rename `aion2dpsmeter.exe` to `aion2dpsmeter.bad.exe`, `aion2dpsmeter.prev.exe` to `aion2dpsmeter.exe`, and the same for `WebView2Loader.prev.dll` → `WebView2Loader.dll` if it is there. Start `aion2dpsmeter.exe`. If `aion2dpsmeter.exe` is missing altogether (the PC lost power during an update), just rename `aion2dpsmeter.prev.exe` to `aion2dpsmeter.exe`.
4. Or download the kit of the version you had from [`releases/`](releases/) and unzip it over the old folder (your settings and fights are kept elsewhere, see [PRIVACY.md](PRIVACY.md)).
5. Send `%LOCALAPPDATA%\Aion2DPSMeter\logs\meter.log` and `meter.prev.log` to the owner. They contain file paths with your Windows user name, but no player names.

## Privacy

See [PRIVACY.md](PRIVACY.md) for every request the meter makes, which switch turns it off, and what it keeps on your PC. In short: there is no telemetry, and your fights stay on your PC.

## Feedback

Testers send feedback to the owner directly: screenshots, the recorder zip from test sessions, and `meter.log` when something misbehaves.
