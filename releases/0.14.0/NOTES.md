# Aion2DPSMeter 0.14.0

# Aion2DPSMeter 0.14.0

Your own look, a menu-hide you can check and teach, and deeper fight details.

- **Appearance editor** (Settings → Appearance). Change the text size and colours per part of the meter: overlay header, player rows, bars, footer and status bar, toasts, tool windows, tables, headings, and the nine class colours. A live preview shows each change; every item has its own reset, and "Reset all" can be undone. Three presets: Default, High contrast, Compact. Export saves a theme file in `Documents\Aion2DPSMeter` that you can share; Import loads one (files are checked strictly, and nothing in them is run). A warning shows when text gets hard to read on its background.
- **Hide in game menus, now with diagnostics** (Settings → Capture). The page shows whether the game window was found, whether its picture arrives, and how close each menu check came. "Test now" checks one picture and says plainly what is wrong. "Copy diagnostics" copies a text block without names that you can send us. "Save debug snapshot" saves the picture and the scores; look at it first, since it can show your character name and chat.
- **Teach a menu.** If a menu is missed: press "Teach a menu (3 s)", open the menu in game, then draw a box around its close button. The new check is saved on your PC and works at once.
- **Ctrl+Shift+H hides or shows the meter** at any time, with or without menu detection. You can change the key or turn it off in Settings → Capture.
- **Backup capture.** If the game window's picture cannot be read, the meter switches to copying the screen under the game. While that runs, the meter's windows are left out of every capture, so they do not show in your screenshots or streams. You can also pick the method by hand. More game UI scales are covered (0.8 to 1.3).
- **Fight details: skills that always crit.** Some specialties make a skill always crit (for example Overhead Slam with its crit specialty: 4,075 of 4,075 hits). The crit tile now has a menu, "all" or "no GC": the second leaves those skills out, shows the rate before and after, and marks them in the table. The overlay's crit column can do the same (Settings → Meter, off by default).
- **Fight details: stagger windows.** When a boss's guard breaks, it is staggered for about 5 s. New tabs, "All combat skills / Stagger windows N", show each window's DPS and skills, or all windows combined. In our recordings the party deals about 1.8 × its normal damage rate in these windows.
- **Fight details: target picker and columns.** In fights with several targets, pick one to narrow the numbers to it; the Healing tab can do the same per healed player. A "Columns" menu hides the skills-table columns you don't need.
- **Gear window:** the "weakest" tag in the side panel is no longer cut off.
- Note: fights saved by 0.14.0 use a new log format. If you roll back to 0.13.0 they don't open there, but they are kept and open again after you update.
