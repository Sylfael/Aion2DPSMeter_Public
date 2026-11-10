# Aion2DPSMeter 0.22.0

# Aion2DPSMeter 0.22.0

Fewer windows, a tidier overlay, one name for each thing. This is the last version before 1.0. Nothing about what the meter measures has changed.

- **A new footer on the overlay.** One button per window, then **More** and click-through. The capture status now starts with its state ("Capturing · ExitLag loopback", "Npcap missing"), so when the overlay is narrow the useful part stays. During a fight the buttons step back; they come back when you point at them.
- **More holds the rest.** Every window by name, Copy as image, Reset fight, Hide overlay, the quick settings and Quit. The × is gone from the footer: Hide and Quit are in More and in the tray icon's menu.
- **Ten windows became seven.**
  - **Records** is now a tab of **Fight details** (on the right, under "all fights"). A click on a run opens that fight in the same window.
  - **World, Tickets and Pets** are now three tabs of one window, **Tracker**. It opens where your World window was. Alerts, the Odyle number in the status bar and the pet notice open it on the right tab.
- **One name per thing.** The window with applicants and party members is called **Party** everywhere. "eDPS" is now simply **DPS** (the number is the same). "Boss fights only" is the same checkbox in More, in Settings and in the tray menu.
- **Small fixes.**
  - The meter no longer shows a brief "Not updating" after the PC wakes from sleep or the clock changes.
  - If the meter's core keeps failing slowly (more than ten restarts in an hour), it now stops and says so instead of restarting for ever.
  - An update no longer ends with no meter running when the old version is slow to close.
  - Decode errors turn the capture dot amber.

If you roll back to 0.21.0, your old windows come back at their old places.
