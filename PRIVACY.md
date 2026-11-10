# Privacy

Aion2DPSMeter reads the game's network traffic on your own PC. Everything it measures stays there. This page lists every request the meter makes over the internet, what it writes on your PC, and which switch turns each one off. It describes version 0.21.0.

## What it sends, and to whom

Every request goes over HTTPS to a fixed list of hosts that is built into the program. Each kind of request can only reach its own hosts, and redirects to other hosts are refused.

| To | What | When | Off switch |
|---|---|---|---|
| **NCSOFT's official armory** (`api-search.plaync.com`, `aion2.plaync.com`) | A player's character name and server, to read their public profile (gear, item level, combat power): a search, then the profile and the equipment, about 3 requests per player | When a look-up runs: you click "Look up" or "Look up all"; you open the Party window yourself (the players listed in it are looked up); the Party window opens itself for a new applicant (⚙ Party → "Open on new applicants") or when you join or form a party (⚙ Party → "Open when you join a party"), and the players it opened for are looked up; or ⚙ "Look up automatically" is on | Turn off the two "Open…" options and "Look up automatically"; then only your clicks look anyone up |
| **NCSOFT's official armory** (`aion2.plaync.com`) | The same name and server, to read each equipped item's page for "Count +ranks and score gear": about 20 more requests per player | When you click "Count +ranks", or with every look-up while ⚙ "Count +ranks from gear and Arcana on every look-up" is on | That option (off by default) |
| **NCSOFT's official armory** (`api-search.plaync.com`, `aion2.plaync.com`) | Your own character's name and server, to find its armory id so "Open in aion2-tools" can open it directly | Only when you click "Link my armory" in the Gear window, once per character. The meter never looks your own character up by itself | Do not click it |
| **abysslogs.com** (`api.abysslogs.com`) | A player's name and server, to show their rank on the card; and the public DPS statistics of the ranked fight (only the region and the fight are sent) | With each armory look-up while ⚙ "Ranks from abysslogs" is on | "Ranks from abysslogs" |
| **abysslogs.com** (`api.abysslogs.com`) and **abysslogs' file storage** (`abyss-logs.<account>.r2.cloudflarestorage.com`, Cloudflare R2) | For players who show their runs on abysslogs: their runs on the room's boss, then the file of their best run, from abysslogs' own storage (the address abysslogs gives for it) | While both ⚙ "Ranks from abysslogs" and ⚙ "Best public parse" are on: with each look-up, and when you open a player's row in the Party window (▾) or click "fetch" on its parse line | Either of the two; with "Ranks from abysslogs" off, nothing at all is sent to abysslogs |
| **GitHub** (`raw.githubusercontent.com`, the public repositories `Not4You-Dev/NotMeter-Global-Ranking-Cache` and `Not4You-Dev/NotMeter-Global-Combat`) | The public Global ranking files that notmeter.com shows on its website: a small pointer file, the ranking's index (about 1.5 MB, once per session), one 2.5 MB index shard chosen by two characters of a hash of the player's name, server and class (**the name itself is never sent**; the match happens on your PC), and, when the player placed in a top 20 with their name shown, that board and one detail file. Players who hid their name on that site, or never placed in a top 20, show as "no public parse". Nothing from these files is kept on disk | With each look-up while ⚙ "Best public parse" is on, at most 200 MB per session for the automatic ones (a click goes past that) | "Best public parse"; then nothing is asked of GitHub except the update check and the downloads you click |
| **GitHub** (`raw.githubusercontent.com`, this repository) | A request for `latest.json`. GitHub sees your IP address and the meter's version. Nothing else is sent | **5 seconds after the meter starts**, then every 6 hours while it runs, while ⚙ "Check for updates" is on; and when you click "Check now" | "Check for updates" |
| **GitHub** (`raw.githubusercontent.com`, `github.com`, and `objects.githubusercontent.com` when GitHub redirects a download there; this repository only) | The download of the new kit | Only when you click "Update now" | Do not click it |
| **NCSOFT's image server** (`assets.playnccdn.com`) | Requests for the game's own skill, buff and class icons. NCSOFT sees your IP address and which icons are shown. No names, numbers or fight data are sent | While ⚙ "Load icons from NCSOFT" is on, when a window shows an icon | "Load icons from NCSOFT" |

**How each service sees the meter.** The update check, the kit download, abysslogs and the public ranking files are sent with a user agent that names the program: `Aion2DPSMeter/<version> (update check)` for the updates, `Aion2DPSMeter/<version> (private, non-commercial)` for abysslogs and the ranking files. **The armory requests to NCSOFT are sent with the user agent of a Chrome browser on Windows** (`Mozilla/5.0 (Windows NT 10.0; Win64; x64) … Chrome/130.0.0.0 Safari/537.36`), not with the program's name, so the armory cannot tell them from a player reading the armory in a browser. No cookies, no account and no login are sent to any service. The icon requests come from the meter's built-in web view, as a browser would send them.

The **self-check** (Settings → About, only when you run it) sends one small request to each of the hosts above that the meter already uses (the update manifest, the armory, abysslogs if its ranks are on, the public ranking pointer if "Best public parse" is on) to see whether they answer; no player name is sent. Its "Copy report" text contains no player names.

**Defaults.** When you first start the meter, these are **on**: "Check for updates", "Ranks from abysslogs", "Best public parse", "Load icons from NCSOFT", "Open on new applicants" and "Open when you join a party" (the Party window), and "Hide in game menus" (which sends nothing). These are **off**: "Look up automatically", "Count +ranks from gear and Arcana on every look-up", "Game FPS in the status bar", "Open Tracker on alerts". Turn off in ⚙ what you do not want.

## Links that open in your browser

These buttons only build a link and hand it to your browser; the meter itself sends nothing. What the website then sees is between you and it.

- "Open party in aion2-tools": the aion2-tools party check, with the party's names and servers in the link.
- "Open in aion2-tools" in the Gear window: the character's server and either its name or, after "Link my armory", its armory id.
- A player's page on **abysslogs.com**.
- A player's page on **AionFlex** (`aionflex.gg`): their server and name in the link.

## What it never sends

- **Combat logs or fight data.** Damage, skills, buffs and the fight history are kept only on your PC.
- **Share images.** The share button puts an image of the fight on your clipboard (or saves it in `Documents\Aion2DPSMeter\`); nothing is uploaded. Where you paste it is up to you, and "Hide other players' names" replaces their names with their class.
- **Your gear.** The Gear window scores items on your PC with aion2-tools' tables, which ship inside the meter; no item is sent anywhere to be scored.
- **Other players' data to any server of ours.** There is no server of ours. Names go only to the armory and abysslogs look-ups above.
- **Telemetry**: no analytics, usage statistics or automatic crash reports.
- **The game traffic itself.** The meter does not upload it, and it never sends anything to the game.
- **Pictures of your screen.** "Hide in game menus" looks at small parts of the game window on your PC to notice an open menu; nothing is sent. If the game window's picture cannot be read, it copies the part of the screen under the game instead, the same way. A picture is saved only when you press "Save debug snapshot" or "Teach a menu" in Settings → Capture (see below); "Copy diagnostics" copies text without names to your clipboard, and you decide whether to send it.
- **Frame timing.** ⚙ "Game FPS in the status bar" (off by default) reads only the frame-timing events (DXGI "Present") that Windows' event tracing (ETW) reports for the game's process, and counts them per second. It does not touch the game or read its memory. Nothing is saved or sent.
- **Your ping.** The status bar's ping comes from the times of the game's own ping messages and its answers in the traffic the meter already reads; only the time and size of the game's outgoing packets are used, never their content. Nothing is sent.
- **The log.** `meter.log` stays on your PC; you decide whether to send it to someone.

## What it keeps on your PC

**`%APPDATA%\dev.sylfael.aion2dpsmeter\`** (the meter's data folder):

| File or folder | What it holds |
|---|---|
| `history\` | The fight history (up to 300 fights or 512 MiB): every player's name, class, damage, skills and buffs in each saved fight |
| `party-store.json` | Your notes and black or white lists for players, with their names and servers. "Export" in Settings → Party writes them to a file in `Documents\Aion2DPSMeter\` that you choose to keep or share |
| `people.json` | What your fights saw of other players: for each player in your fights, their name and server, the specialties of their skills as last seen, how many fights you shared and the last date |
| `together.json` | Runs with other players: for each player you fought a boss beside, the date, boss, DPS, share and deaths of your last 20 fights together, and their skill shares in the latest long kill. Rebuilt from the fight history when deleted |
| `trend.json` | Rank snapshots for players you looked up with "Ranks from abysslogs" on: one point per day (rank for the room's dungeon, a DPS estimate, combat power), at most 60 per player, with their name and server. Players not looked up for 90 days are dropped |
| `records.json` | Your personal bests: for each boss, your own characters' best DPS, fastest kill and last 20 runs (date, DPS, length, party DPS, deaths). Only your own characters' names. Rebuilt from the fight history when deleted |
| `tickets.json` | Your own characters' tickets and energy: their names, server, class, when you last played them, the ticket counts and memberships the game sent. Only characters that logged in while the meter ran; "Forget" in the Tickets window removes one |
| `gear.json` | Your own characters' gear: their names and server, their equipped, bag and warehouse items, Exchange purchases, enchant attempts and re-engraves, and the armory id once you clicked "Link my armory". Only characters that logged in while the meter ran. **Players you inspect are never stored**: their profiles, gear and public parses are held in memory until you quit |
| `world.json`, `pets.json` | The field-boss timers, your alert choices and your pet collection (no player names) |
| `protocol-builds.json` | The game builds you marked as verified |
| `overlay-window.json`, `windows.json` | Where the overlay and the other windows were |
| `core-settings.json` | A copy of your ⚙ settings (switches and values, no names), so the meter applies them from the first second |
| `menus\` | Menu checks you taught: small crops of the game's menus |
| `menu-debug\` | Only when you press "Save debug snapshot": a picture of the game window, which can show your character name and chat, and the match scores. Delete the folder any time |
| `updates\` | `state.json` (the version kept for "Roll back", a version you chose to skip, a version that did not start after an update); while an update runs: the download (deleted once installed), `cleanup.json`, `watch.json` and a `started-….ok` marker (deleted once the new version has started) |

**`%LOCALAPPDATA%\Aion2DPSMeter\logs\`**: `meter.log`, a diagnostic log, and `meter.prev.log`, the log of the run before. A new log starts with each start (a start after an update adds to the last one). It contains no player names, but it does contain file paths, such as the folder the meter runs from and the files you export, and **those paths include your Windows user name**. Look through it before you send it to someone.

**`%LOCALAPPDATA%\dev.sylfael.aion2dpsmeter\`**: the app's web view data, which holds the ⚙ settings and your theme.

**`Documents\Aion2DPSMeter\`**: only what you save there yourself: share images (when the clipboard is not used), "Export" of your notes and lists, your theme, and the pet export for aion2-tools.

**Next to the meter** (the folder you unzipped): after an update, `app\aion2dpsmeter.prev.exe` and `app\WebView2Loader.prev.dll`, the previous version, kept for "Roll back".

To remove everything, quit the meter, then delete the folder you unzipped and the four folders above.
