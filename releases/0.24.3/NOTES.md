# Aion2DPSMeter 0.24.3

# Aion2DPSMeter 0.24.3

The meter no longer goes missing. No change to any number.

- **A left click on the tray icon never hides the meter any more.** It always brings the overlay back and puts right whatever was stuck (as "Reset windows (unstick)" does). A single click on the tray icon used to hide the overlay without a word, which looked like the meter had disappeared. To hide the overlay on purpose, use "Hide overlay" in the tray menu (right click).
- **Ctrl+Shift+M brings back a hidden overlay.** When the overlay is hidden, the click-through key shows it again and leaves click-through as it was. When it is shown, the key turns click-through on or off as before.
- **The overlay stays above the game.** If the game window ends up on top of the overlay, the meter puts the overlay back on top within a few seconds, without taking the focus from the game. Other programs' windows are left alone. In true exclusive fullscreen the overlay is not forced over the game.
- **"Reset windows (unstick)" says what it fixed** in `meter.log` (hidden, off screen, or under the game), and so does each time the overlay is put back on top. If the meter still goes missing, send `meter.log`.
