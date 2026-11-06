# Privacy

Aion2DPSMeter reads the game's network traffic on your own PC. Everything it measures stays there. This page lists every request the meter makes over the internet.

## What it sends, and to whom

| To | What | When |
|---|---|---|
| **NCSOFT's official armory** (`api-search.plaync.com`, `aion2.plaync.com`) | The character name and server of a party applicant or member, to read their public profile (gear, item level, combat power) | When a look-up runs: you click it, the inspector opens itself for new applicants (⚙ "Open inspector on new applicants"), or ⚙ "Look up automatically" is on |
| **abysslogs.com** (`api.abysslogs.com`) | The same name and server, to show their rank on the card | Only while ⚙ "abysslogs ranks" is on, together with an armory look-up. Turn it off and nothing is sent there |
| **GitHub** (`raw.githubusercontent.com`) | A request for `latest.json` in this repository, with the user agent `Aion2DPSMeter/<version> (update check)`. GitHub sees your IP address and the meter's version. Nothing else is sent | 30 s after start, then every 6 h, while ⚙ "Check for updates" is on; and when you click "Check now" |
| **GitHub** (`raw.githubusercontent.com`) | The download of the new kit | Only when you click "Update now" |
| **NCSOFT's image server** (`assets.playnccdn.com`) | Requests for the game's own skill, buff and class icons. NCSOFT sees your IP address and which icons are shown. No names, numbers or fight data are sent | While ⚙ "Load icons from NCSOFT" is on (from 0.8.0), when a window shows an icon. Turn it off and nothing is fetched |

Defaults: "abysslogs ranks", "Check for updates", "Load icons from NCSOFT" and "Open inspector on new applicants" are **on** when you first start the meter. "Look up automatically" is off. Turn off in ⚙ what you do not want.

Two buttons open a page in **your browser** instead, and only when you click them:

- the aion2-tools party check, whose link contains the party's names and servers;
- a player's abysslogs.com page.

## What it never sends

- **Combat logs or fight data.** Damage, skills, buffs and the fight history are kept only on your PC.
- **Other players' data to any server of ours.** There is no server of ours. Names go only to the armory and abysslogs look-ups above.
- **Telemetry**: no analytics, usage statistics or automatic crash reports.
- **The game traffic itself.** The meter does not upload it, and it never sends anything to the game.
- **Pictures of your screen.** "Hide in game menus" (from 0.8.0) looks at small parts of the game window on your PC to notice an open menu; nothing is saved or sent.

## What it keeps on your PC

- `%APPDATA%\dev.sylfael.aion2dpsmeter\`:
  - the fight history (up to 300 fights or 512 MiB);
  - your notes and black or white lists for players;
  - the overlay's position;
  - the game builds you marked as verified;
  - the field-boss timers, alert choices and your pet collection (`world.json`, `pets.json`; no player names);
  - update downloads (deleted once installed).
- `%LOCALAPPDATA%\Aion2DPSMeter\logs\meter.log`: a diagnostic log, rewritten at each start. It contains no player names.
- `%LOCALAPPDATA%\dev.sylfael.aion2dpsmeter\`: the app's web view data, which holds the ⚙ settings.

- `Documents\Aion2DPSMeter\`: pet exports, only when you click "Export for aion2-tools".

Looked-up profiles are held in memory only.

To remove everything, quit the meter, then delete its folder and the three folders above.
