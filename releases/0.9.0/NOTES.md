# Aion2DPSMeter 0.9.0

New in 0.9.0:
- Tickets window (tray "Tickets…" or the ticket button at the bottom of the meter): one row for each of your characters that logged in while the meter ran, with when you last played it. It shows Odyle energy, Nightmare tickets, Ascension Trial, the daily dungeon, Shugo keys, Invasion keys and how many days your memberships have left.
- Odyle is shown like in the game, "25 (+500)": your normal energy and, after the plus, the extra energy from items. The meter adds the +15 that comes back every 3 hours (at 01:00, 04:00, 07:00 … UTC), also for characters you are not playing; such a number has a "~" in front. This was checked against the game: what the meter predicted is what the game showed at the next login.
- The other tickets are shown as you last saw them, with the time. The game's daily and weekly reset times are not known for sure yet, so the meter does not guess them; a small ↻ says that a reset has passed since and the real number is probably higher.
- Status bar: a slim line under (or over) the meter with your character, its Odyle, your ping and, if you turn it on, the game's FPS. It can stay visible while the meter is faded, a strip or hidden. Settings ⚙ → "Status bar".
- The ping is the game's own ping: the time from the game's ping message to the server's answer, measured on your PC. With ExitLag it is the whole way through ExitLag to the game server, not only to ExitLag.
- Game FPS (off by default): counted from Windows' own frame-timing events for the game, the way PresentMon does it. Nothing touches the game. Windows allows this only for administrators and the "Performance Log Users" group; if you are not in it, the bar says so and ⚙ shows how to add yourself (one command, then sign out and in).
- Optional alerts "Odyle full" and "Nightmare tickets at cap" (off by default), with the same toast and sound as the field-boss alerts.

Your characters' names and tickets are saved only on your PC (tickets.json in the app data folder). Nothing new is sent anywhere.

Requirements: Windows 10 or 11 and Npcap.
