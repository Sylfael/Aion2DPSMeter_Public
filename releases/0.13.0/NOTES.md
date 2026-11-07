# Aion2DPSMeter 0.13.0

# Aion2DPSMeter 0.13.0

Gear: your items, how good their lines and stones are, and what to reroll next.

- **A new Gear window** (tray → "Gear…"). The game sends your whole inventory when you log in, and the meter reads it from the same traffic it already reads for damage. The window lists what you wear, what is in your bag and warehouse, what you bought on the Exchange, and your enchant attempts and manastone re-engraves. It also shows the gear of players you inspect in game. Each of your characters keeps its own page; pick one at the top.
- **Scores from aion2-tools.** Every piece gets two numbers: how close its soul-binding lines and its manastones are to the best this item can roll, for the build you pick at the top (the build's stat weights are aion2-tools' estimates, not official). The window also says what to do next ("Sync line 2, 58 %" means one Sync of that line has a 58 % chance to roll something better; "Re-engrave 80 %", "Reset"). Click a row to see each line, each stone, the odds and the recent upgrades of that piece; "Copy as text" copies it all. Items with fixed lines (no soul binding, such as some bracelets) are marked "fixed" and never get Sync advice. Arcana show their god stat; aion2-tools plans Arcana in its own planner, so they get no score here.
- **Open in aion2-tools.** A button in each item's panel opens your character in aion2-tools in your browser. Click "Link my armory" once at the top of the Gear window and the button opens your character directly. Without it, aion2-tools looks the character up first. "Link my armory" asks the official armory about your character once, and only when you click it.
- **Optional toast.** Settings → Alerts → Gear ("New piece beats equipped") can show a short message over the meter when a piece you loot or buy beats what you wear in that slot. It is off by default.
- **Manastone values checked against the Global armory.** The game names the stone, the stat and the tier but not the value, so the meter takes the value from NCSOFT's published tables. We compared them with the official Global armory for 32 sockets on 8 items, and all 32 matched.
- Inspected players are kept only until you quit. Your own characters' gear is saved on your PC (`gear.json`) so the window is filled before your next login.
