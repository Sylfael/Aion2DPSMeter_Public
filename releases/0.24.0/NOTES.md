# Aion2DPSMeter 0.24.0

# Aion2DPSMeter 0.24.0

What each buff added to the party's damage.

- **New Buffs tab in Fight details.** For each player in your party (at most 5), it shows their damage, how much of it came from other players' buffs ("from others"), how much their own buffs added to the others' damage ("to others"), and the result as rDPS: the damage per second with each buff's part moved to the player who cast it. A second list shows each buff and debuff that helped the party, with how much damage it added and its share of all the damage. Click one to see who it helped and how much damage was done while it was up.
- **Estimates from measured values.** The buff values come from the meter's own measurements over many fights. Only damage increases are counted: combat speed, cooldown and critical hit effects are left out, and the tab names what it did not count. When two players cast the same buff, the higher skill level gets the credit. A buff only counts on a player it was actually seen on, and a debuff on the hits made while it was on the target.
- **Party only.** Players outside your party are grouped on one line. Fights with no party, fights where the game does not send the other players' hits, and fights recorded before 0.24.0 show a short message instead of the table. After each fight the meter checks that the shares add up to the party's damage; when they do not, the tab says the fight could not be worked out rather than show wrong numbers.
- **Fight files** now keep the party's buffs, so they are a little bigger. If you go back to an older version, fights saved by 0.24.0 stay in the list but cannot be opened there.
