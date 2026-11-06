# Aion2DPSMeter 0.8.0

New in 0.8.0:
- Skill and buff names with their icons in the fight details window: the skills table, the opener, the buffs on you and on the target, and the death recap. Hover a skill to see its active specialties.
- The game's official class emblems, in the class colours, on the meter, the inspector cards and the fight details. ⚙ "Class icons" chooses Official (class colour), Official (silver), Simple (our own icons) or Off.
- New colour for the Chanter: orange.
- Icons and emblems are loaded from NCSOFT's own image server while ⚙ "Load icons from NCSOFT" is on (the default). Turn it off and nothing is fetched: you see names and our own class icons only.
- World window (tray "World…" or the globe button on the meter): field-boss timers per map, shown as up, spawns in m:ss, due, dead or unknown, with how old the list is. Open the world map in game (Field Boss tab) once to fill it; the timers are kept between runs. All 24 Altgard field bosses are named.
- Field-boss alerts: pick a boss in the World window and choose how many minutes before (for example 5 and 1) and/or when it spawns. The meter shows a notice and plays a short tone (⚙ "Alert sound" and "Alert volume"). "Open World window on alerts" is off by default.
- Pets window (tray "Pets…" or the paw button): your pet collection per board with levels, souls and what is maxed, your soul crystals, and the Black Cloud merchant's offers marked as unlocks, levels up, useful or wasted, with price and discount. "Export for aion2-tools" saves a file in Documents\Aion2DPSMeter.
- Hide in game menus (first version): the meter fades out while a full-screen game window is open (inventory, map, skills, shop…) and comes back when you close it. ⚙ "Hide in game menus" (on), "Keep visible in combat" (on) and a sensitivity choice. If your PC cannot capture the game window, ⚙ says "capture unavailable" and the meter simply stays visible. Please tell us if it hides at the wrong time or never hides.
- Applicant and party cards show a server tag when a player comes from another server, outlined when they are from the other faction.
- When you lead a room, the inspector now notices when you decline an applicant and when an applicant withdraws (or joins another room), and drops their card.
- Open-world field bosses where the game does not send other players' damage are detected by themselves: the meter shows your damage only and says so, instead of a meaningless party DPS.
- The inspector no longer reopens itself right after you close it. After a close it waits 60 s before opening for a party again (20 s for a new applicant), people already seen in your room or party in the last 30 minutes never reopen it (zone changes and dungeon entry used to), and a minimised inspector stays minimised. meter.log says why it opened or stayed closed.
- Full monster names: more than 7,000 monsters are now named.
- "Grow upwards" now keeps the normal layout (header on top, rank 1 first, buttons at the bottom); the window still keeps its bottom edge, so a strip parked at the bottom of the screen grows upwards into the full meter.

Requirements: Windows 10 or 11 and Npcap.
