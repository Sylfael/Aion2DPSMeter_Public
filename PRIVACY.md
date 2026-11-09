# Privacy

Aion2DPSMeter reads the game's network traffic on your own PC. Everything it measures stays there. This page lists every request the meter makes over the internet.

## What it sends, and to whom

| To | What | When |
|---|---|---|
| **NCSOFT's official armory** (`api-search.plaync.com`, `aion2.plaync.com`) | The character name and server of a party applicant or member, to read their public profile (gear, item level, combat power) | When a look-up runs: you click it, the inspector opens itself for new applicants (⚙ "Open inspector on new applicants"), or ⚙ "Look up automatically" is on |
| **NCSOFT's official armory** (`api-search.plaync.com`, `aion2.plaync.com`) | Your own character's name and server, to find its armory id so "Open in aion2-tools" can open it directly | Only when you click "Link my armory" in the Gear window (from 0.13.0), once per character. The meter never looks your own character up by itself. abysslogs.com is not asked |
| **abysslogs.com** (`api.abysslogs.com`) | The same name and server, to show their rank on the card. From 0.19.0, when they show their runs there: their runs on the room's boss, then that run's file from abysslogs' own storage | Only while ⚙ "abysslogs ranks" is on, together with an armory look-up (the runs: with each look-up while ⚙ "Best public parse" is on). Turn it off and nothing is sent there |
| **GitHub** (`raw.githubusercontent.com`, the public repositories `Not4You-Dev/NotMeter-Global-Ranking-Cache` and `Not4You-Dev/NotMeter-Global-Combat`) | The public Global ranking files that notmeter.com shows on its website: a small pointer file, the ranking's index (about 1.5 MB, once per session), one 2.5 MB index shard chosen by two characters of a hash of the player's name, server and class (**the name itself is never sent**; the match happens on your PC), and, when the player placed in a top 20 with their name shown, that board and one detail file. Players who hid their name on that site, or never placed in a top 20, show as "no public parse". Nothing from these files is kept on disk | From 0.19.0, with each look-up while ⚙ "Best public parse" is on (on by default; at most 200 MB per session automatically). Turn it off and nothing is asked of GitHub except the update check and the downloads you click |
| **GitHub** (`raw.githubusercontent.com`) | A request for `latest.json` in this repository, with the user agent `Aion2DPSMeter/<version> (update check)`. GitHub sees your IP address and the meter's version. Nothing else is sent | 30 s after start, then every 6 h, while ⚙ "Check for updates" is on; and when you click "Check now" |
| **GitHub** (`raw.githubusercontent.com`) | The download of the new kit | Only when you click "Update now" |
| **NCSOFT's image server** (`assets.playnccdn.com`) | Requests for the game's own skill, buff and class icons. NCSOFT sees your IP address and which icons are shown. No names, numbers or fight data are sent | While ⚙ "Load icons from NCSOFT" is on (from 0.8.0), when a window shows an icon. Turn it off and nothing is fetched |

The **self-check** (Settings → About, from 0.20.0, only when you run it) sends one small request to each of the hosts above that the meter already uses (the update manifest, the armory, abysslogs if its ranks are on, the public ranking pointer if "Best public parse" is on) to measure whether they answer; no name is sent. Its "Copy report" text contains no player names.

Defaults: "abysslogs ranks", "Check for updates", "Load icons from NCSOFT" and "Open inspector on new applicants" are **on** when you first start the meter. "Look up automatically" is off. Turn off in ⚙ what you do not want.

Two buttons open a page in **your browser** instead, and only when you click them:

- the aion2-tools party check, whose link contains the party's names and servers;
- "Open in aion2-tools" in the Gear window (from 0.13.0), whose link contains the character's server and either its name or, after "Link my armory", its armory id;
- a player's abysslogs.com page; from 0.18.0, opening a player's row in the inspector (▾) also asks abysslogs for that player's best public run on the room's boss (only if they show their runs there): their name and server, then that run's file;
- from 0.18.0, "Count +ranks and score gear" (a click, or the ⚙ option "on every look-up", off by default) reads each equipped item's page on the official armory: about 21 requests per player, with the same name and server.

## What it never sends

- **Combat logs or fight data.** Damage, skills, buffs and the fight history are kept only on your PC.
- **Share images.** The share button puts an image of the fight on your clipboard (or saves it in `Documents\Aion2DPSMeter\`); nothing is uploaded. Where you paste it is up to you, and "Hide other players' names" replaces their names with their class.
- **Your gear.** The Gear window (from 0.13.0) scores items on your PC with aion2-tools' tables, which ship inside the meter; no item is sent anywhere to be scored.
- **Other players' data to any server of ours.** There is no server of ours. Names go only to the armory and abysslogs look-ups above.
- **Telemetry**: no analytics, usage statistics or automatic crash reports.
- **The game traffic itself.** The meter does not upload it, and it never sends anything to the game.
- **Pictures of your screen.** "Hide in game menus" (from 0.8.0) looks at small parts of the game window on your PC to notice an open menu; nothing is sent. From 0.14.0, if the game window's picture cannot be read, it copies the part of the screen under the game instead, the same way. A picture is saved only when you press "Save debug snapshot" or "Teach a menu" in Settings → Capture (see below); "Copy diagnostics" copies text without names to your clipboard, and you decide whether to send it.
- **Frame timing.** ⚙ "Game FPS" (from 0.9.0, off by default) reads only the frame-timing events (DXGI "Present") that Windows' event tracing (ETW) reports for the game's process, and counts them per second. It does not touch the game or read its memory. Nothing is saved or sent.
- **Your ping.** The status bar's ping (from 0.9.0) comes from the times of the game's own ping messages and its answers in the traffic the meter already reads; only the time and size of the game's outgoing packets are used, never their content. Nothing is sent.

## What it keeps on your PC

- `%APPDATA%\dev.sylfael.aion2dpsmeter\`:
  - the fight history (up to 300 fights or 512 MiB);
  - your notes and black or white lists for players ("Export" in Settings → Party, from 0.17.0, writes them with the players' names to a file in `Documents\Aion2DPSMeter\` that you choose to keep or share);
  - the overlay's position;
  - the game builds you marked as verified;
  - the field-boss timers, alert choices and your pet collection (`world.json`, `pets.json`; no player names);
  - your own characters' tickets and energy (`tickets.json`, from 0.9.0): their names, server, class, when you last played them, the ticket counts and memberships the game sent. Only characters that logged in while the meter ran; "Forget" in the Tickets window removes one;
  - your own characters' gear (`gear.json`, from 0.13.0): their names and server, their equipped, bag and warehouse items, Exchange purchases, enchant attempts and re-engraves, and the armory id once you clicked "Link my armory". Only characters that logged in while the meter ran. **Players you inspect are never stored**: their gear is held in memory until you quit;
  - menu checks you taught (`menus/`, from 0.14.0): small crops of the game's menus;
  - debug snapshots (`menu-debug/`, from 0.14.0), only when you press "Save debug snapshot": a picture of the game window, which can show your character name and chat, and the match scores. Delete the folder any time;
  - your personal bests (`records.json`, from 0.16.0): for each boss, your own characters' best DPS, fastest kill and last 20 runs (date, DPS, length, party DPS, deaths). Only your own characters' names are kept; delete the file to reset them (it is rebuilt from the fight history);
  - what your fights saw of other players (`people.json`, from 0.18.0): for each player in your fights, their name and server, the specialties of their skills as last seen, how many fights you shared and the last date;
  - runs with other players (`together.json`, from 0.18.0): for each player you fought a boss beside, the date, boss, DPS, share and deaths of your last 20 fights together, and their skill shares in the latest long kill. Rebuilt from the fight history when deleted;
  - rank snapshots (`trend.json`, from 0.18.0): for players you looked up with abysslogs ranks on, one point per day (rank for the room's dungeon, a DPS estimate, CP), at most 60 per player; players not looked up for 90 days are dropped;
  - update downloads (deleted once installed).
- Your theme (from 0.14.0) is kept with the app's settings. "Export" writes it to `Documents\Aion2DPSMeter\`; a theme file holds only sizes and colours.
- `%LOCALAPPDATA%\Aion2DPSMeter\logs\meter.log`: a diagnostic log, rewritten at each start. It contains no player names.
- `%LOCALAPPDATA%\dev.sylfael.aion2dpsmeter\`: the app's web view data, which holds the ⚙ settings.

- `Documents\Aion2DPSMeter\`: pet exports, only when you click "Export for aion2-tools".

Looked-up profiles are held in memory only; so are public parses (from 0.19.0).

To remove everything, quit the meter, then delete its folder and the three folders above.
