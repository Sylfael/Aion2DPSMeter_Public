# Aion2DPSMeter 0.23.0

# Aion2DPSMeter 0.23.0

Three new things before the meter is frozen for testing, and Quit no longer loses a fight.

- **Phase thresholds on the boss HP bar.** For bosses the meter knows, small marks on the overlay's boss HP bar show the HP at which the next phases usually start, so you see them coming. The next one stands out in blue and is also written as text ("next 52%"); the ones you passed turn dim. Fight details shows the same thresholds as dashed lines on the boss HP line. The thresholds come from past recordings and can differ by a few points; bosses the meter does not know get no marks.
- **Dungeon run times.** The meter times each dungeon run with the game's own clock, from the moment the run starts (the end of the entry wait) to the clear. After a clear the overlay shows the run next to the last one, for example "Run 5:06 · last 5:42 · −36 s" (green when faster, red when slower, "new best" when it is). The Records tab of Fight details has a new "Dungeon runs" section: per dungeon and difficulty (and per Nightmare boss) your best and last runs, and a click shows the last 20. Only cleared runs count. The times are kept in a new file, `runs.json`, next to your other meter files.
- **CP and gear score next to the names (off by default).** Settings → Overlay → Rows has two new switches, Show CP and Show gear score. When on, each player's CP and gear score are written after the name, when the meter knows them. Nothing new is looked up. When the overlay is narrow, the numbers give way so the names and DPS stay readable.
- **Quit saves the fight in progress.** Quitting the meter (tray or More → Quit, or an update) now ends and saves the running fight, as Reset fight does.
- **Records updates by itself** when a run is cleared while the tab is open, and Settings → Privacy lists the new run times file.
