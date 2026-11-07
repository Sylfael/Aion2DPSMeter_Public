# Aion2DPSMeter 0.15.0

# Aion2DPSMeter 0.15.0

A popup for pet souls, and menu detection that recovers by itself.

- **Pet soul popup.** When you gain pet souls, a small toast over the meter shows the pet, "+N souls" and its progress ("Lv 1 · 12 / 25"), with its board's colour. It says when a pet unlocks, levels up or reaches max. Several gains for the same pet in a row merge into one toast; click it to open the Pets window. If the meter started after you logged in, the toast still shows the gain and asks you to relog to see the progress. Settings → Alerts → Pets: on by default, "Skip maxed pets", and how long it stays (8 s).
- **Pets window: "This session".** A strip at the top lists the souls you gained since the meter started, per pet, newest first.
- **Hide in game menus recovers by itself.** If the capture failed several times in a row (for example while the game was loading), detection used to stay off until you changed a setting. It now tries again by itself every 30 s.
- **Hide in game menus knows the back arrow.** Pages without a close X, such as a shop item's purchase page, show a back arrow in the top-right corner; the meter now hides on those too.
