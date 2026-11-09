# Aion2DPSMeter 0.19.0

# Aion2DPSMeter 0.19.0

A player's best public parse, more often, and as soon as they apply.

- **Best public parse on every row.** When the inspector looks someone up (it opens itself for new applicants and when you join a party), it also looks for their best public parse: first their runs on abysslogs if they show them, then the public Global ranking. The row shows it compactly ("61k · top 4.0 % · 3 Nov · ranking"), and the details show the kill, its length and a per-skill table, which the rotation hints use too. Players with no public parse simply show "no public parse", never a flag.
- **Polite and bounded.** Cheap checks come first; the big downloads run only when a player actually has a parse, wait while you are in a fight, and stop at 200 MB per session (a click on "fetch" still works). Nothing from these files is kept on disk, and the ranking is asked by two characters of a hash: your applicants' names are never sent to it. Players who hid their name on that ranking show nothing. Settings → Party → "Best public parse" (on) turns it off.
- **The right boss.** A run on abysslogs is a whole dungeon; the inspector now picks the room's boss from it instead of the run's last pull.
- **"View on AionFlex"** link in a player's details.
