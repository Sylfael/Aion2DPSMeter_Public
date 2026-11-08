# Aion2DPSMeter 0.16.0

# Aion2DPSMeter 0.16.0

A timeline of every fight, your personal bests, a share image, toasts above the meter, and a smoother meter in long fights.

- **Smoother in long fights.** The meter did too much work for every network packet during a fight, so in long or crowded fights (world bosses, the Abyss, field bosses with many players) it fell behind the game: the boss HP % and the numbers lagged, more and more as the fight went on. It now rebuilds the numbers only when the overlay updates. This is the "boss HP % in open world" report.
- **Timeline** (Fight details → Timeline): one lane per skill with each hit, crits and presses; your buffs, the boss HP line, stagger windows, deaths and quiet stretches. Hover for details; drag to zoom, and the summary and skills table follow the range. Below it, your **opener**: the skills you pressed in the first 15 s, in order.
- **Compare** (Fight details → Compare): this fight against another run of the same boss, or two players of the same fight, skill by skill, with both timelines on one clock. "Same length" makes it an A/B test on the training dummy: swap a piece of gear, hit for 60 s, compare.
- **Personal bests** (tray → "Records…"): per boss and character, your best DPS, fastest kill, kills and runs, and a small chart of your recent runs. Fight details shows how this run compares, and a toast tells you about a new best (Settings → Alerts → Records).
- **Share image.** The share button (overlay footer, Fight details) copies an image of the fight to the clipboard, ready to paste in Discord: boss, time, party DPS and each player's DPS, share, crit and deaths. Settings → Meter can hide other players' names (they show as their class). Shift+click saves the image to `Documents\Aion2DPSMeter\` instead.
- **Toasts above the meter.** World alerts, pet souls, gear and personal-best toasts now appear in their own strip just above the meter (or below it when the meter sits at the top of the screen), never over the meter itself.
- **Hide in game menus repairs itself.** If the picture stops arriving, freezes, or nothing matches for minutes, detection reopens the capture by itself; after a switch to the screen copy it tries the window capture again later; and "Keep visible in combat" only pauses detection while damage is still going up. Settings → Capture shows the last changes, and Copy diagnostics includes them.
- **Boss tags:** the rule from 0.15.1 that ignores a passer-by's hit no longer splits a long open-world fight where your party's share of the boss is small.
