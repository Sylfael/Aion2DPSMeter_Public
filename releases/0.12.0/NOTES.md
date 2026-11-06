# Aion2DPSMeter 0.12.0

# Aion2DPSMeter 0.12.0

Healing: who healed how much, and who kept whom alive.

- **The meter can show healing.** Choose what the rows show in Settings → Meter ("Overlay shows") or in the meter's quick settings: damage (as before), healing, or both. A click on the party number in the meter's header switches too. Healing rows show HPS, the healing done, the overheal and each player's share of the party's healing. In "both" mode the damage rows get an HPS column and a thin green stripe for the healing; players who only healed are listed at the end. Healing means HP actually restored: overheal (healing on a full or nearly full HP bar) and shields are not counted as healing.
- **A Healing tab in the fight details.** For each player: healing, HPS, overheal, every heal skill (direct heals, heals over time, lifesteal, potions and food, restoration on hit, shields), who they healed and how much, and the healing they received, split by who it came from. A chart shows the party's healing per second, and the selected player's, under the boss HP line, so you can see when the heavy healing happened. "Shielded by" lists whose shields took hits for the player.
- **Shields are no longer counted as damage taken.** Until now, a hit that a shield absorbed could be counted twice in "damage taken". It is counted once now, so **damage taken for shielded players is lower than before**. The fight details show how much of the damage taken each source's hits put into shields ("absorbed"), and how much HP was really lost.
- **Fight history shows HPS.** The fight picker in the fight details lists the party's HPS next to its DPS. Fights saved before 0.12.0 have no healing data; their Healing tab says so.
