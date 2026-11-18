# Aion2DPSMeter 0.24.2

# Aion2DPSMeter 0.24.2

A lighter meter while you play. No new feature and no change to any number.

- **The overlay draws far less during a fight.** The red "live" dot no longer pulses and the boss HP bar no longer slides: both kept the overlay redrawing 60 times a second for the whole fight. It now redraws only when its numbers change.
- **The meter updates twice a second by default** (it was about four). Settings → Meter → Fights → "Refresh rate" offers up to 5 times, 2 times or once a second. At once a second the timer can skip a second now and then, and a kill shows up to a second late.
- **Side windows exist only while they are open.** Party, Fight details, Tracker, Gear and Settings are now built when you open them and removed when you close them, which frees their memory. The first open of a window takes a moment. Gear stays loaded in the background while "New piece beats equipped" is on.
  - What a closed window forgets: the fight and filters picked in Fight details, the rows opened in Party, the character and row selected in Gear, the Pets filter, the last self-check report and the appearance editor's undo. The tab of Party and of Fight details is remembered, and so are a "Teach a menu" crop in progress and a skill chosen but not yet added.
  - Settings → General → Performance → "Keep side windows loaded" brings back the old behaviour (a closed window stays in memory).
- **The game goes first.** The meter's display processes now run at "below normal" priority, so the game wins when the processor is busy. Reading the game's data keeps its normal priority, so no hit is lost. Settings → General → Performance → "Give the game priority" turns it off.
- **Update and roll back from the tray.** The tray menu now has "Update to … available… → Update and restart" when an update is offered, and "Roll back to … → Roll back and restart" when a previous version is kept. Neither needs the Settings window.
- Party and Settings no longer receive anything while they are hidden, the lookup spinner turns in steps, and the overlay's rows build their tooltips with less work.

If a side window does not open, opens behind the game, or anything else looks wrong: tray → "Roll back to 0.24.1 → Roll back and restart".
