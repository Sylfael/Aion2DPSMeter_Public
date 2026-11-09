# Aion2DPSMeter 0.18.0

# Aion2DPSMeter 0.18.0

The inspector learns about players: skills and specialties, gear, your history together, rotation checks, and a forecast for the party.

- **Skills and specialties.** Each looked-up row shows the skills tracked for that class, with their level and the specialties seen in your fights together ("not visible" until then: the official armory does not show specialties). Settings → Party → Tracked skills chooses the skills, wanted specialties and minimum levels per class.
- **+ranks and gear score.** "Count +ranks and score gear" (in the row's details) reads each equipped item's page on the armory: skill levels show their bonus ("Lv 18 (+4)"), and the gear gets a soul-binding and manastone score ("SB 72 · MS 81") from aion2-tools' model, with the list of pieces.
- **Runs with you.** Players you fought a boss with show "3 runs · 2 Nov · 31.2k, 24 % · 1 death"; the details list those fights (click to open them) and offer a memo line you can keep in one click.
- **Rotation checks.** The meter compares a player's skills with what top players of their class do in Raid and Conquest, in the same specialty setup (a Chanter without Dark Crush's Piercing Strike option is compared with top Chanters without it). It shows one hint per row, e.g. "best parse: no Deadshot (top Rangers 21 %)". These are hints only: they never fail a player. From your fights with them, from their armory, or from their best public run on abysslogs when you open their row (if they show their runs there).
- **abysslogs.** For the room's dungeon: their top %, an estimated DPS, clears and their last clear.
- **Rank trend.** Each lookup keeps a small snapshot, so you see "↑ 22 % → 8.5 % in 3 weeks" for players you meet again.
- **Party forecast** (an estimate): the party's estimated DPS against the boss's HP gives a kill time and an enrage risk, also with the open slots filled from the applicants.
- **Leading a room.** A "Best fit" sort (missing roles first), a "hide fails" toggle, the dungeon's minimum item level applied to the verdict, Block/Trust and the memo's first line right on the row, and toasts when a Trust-listed player applies (on) or a strong applicant does (on; Settings → Party → Alerts: your CP + 5,000 or GS + 300, or fixed values).
- **Overlay line.** Under the meter while you lead a room: "4 applicants · 1 fail · healer missing"; click to open the inspector.
- **Full profile** in the row's details: skills, stigmas, passives and Daevanion boards.
