# Aion2DPSMeter 0.19.1

# Aion2DPSMeter 0.19.1

Fixes for windows that could block your clicks, a DPS fix on bosses that turn damage into HP, and a smarter party inspector.

- **No more windows that block clicks.** An inspector or World window that opened by itself could not be closed with its X, and with "Inspector on top" it stayed over the game. It now closes normally. The toast strip above the meter also hides itself if it ever stays up with nothing in it, and a faded or hidden meter always lets clicks through.
- **DPS too high on bosses that turn damage into HP.** Some bosses (Thamon) carry buffs that convert part of the damage they take into HP. The game reports that converted part as a damage-over-time tick from the attacker, and the meter counted it a second time, mostly for magic classes (an Elementalist read about 39 % too high on Thamon). Those ticks are no longer counted as damage; Fight details now shows "boss HP lost … · … absorbed by the boss" so the numbers add up.
- **Unstick without restarting.** Tray → "Reset windows (unstick)" puts the meter back to normal (shown, not faded, toasts hidden, click-through re-applied). Ctrl+Shift+M (click-through) also clears stuck states, and Ctrl+Shift+H hides every meter window.
- **Better logs for reports.** Window changes are written to meter.log, and the previous session's log is kept as `meter.prev.log` next to it: send both after a problem, before restarting the meter twice.
- **Public parses without abysslogs ranks.** The inspector finds the room's boss from the dungeon (18 Conquest, Exploration and Raid modes), so the best-parse search starts even when abysslogs ranks are off or not in yet.
- **Party forecast from real numbers.** Each player's DPS comes from your own kills with them, then their public run or ranking kill, and only then from the abysslogs estimate; the tooltip says which.
