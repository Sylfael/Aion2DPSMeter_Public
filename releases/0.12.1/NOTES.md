# Aion2DPSMeter 0.12.1

# Aion2DPSMeter 0.12.1

Two fixes to the Healing tab.

- **Critical heals show "—" instead of 0.0 %.** Heals do not crit in this game: we checked over 28,000 heals from several recorded sessions, and none of them is marked as a crit or comes out bigger the way a crit would. The same healers' attacks crit about half the time, so the meter does read crits; heals just don't have them. The crit column and the crit tile now show "—", and hovering them says why. The meter's row tooltip no longer says "crit heals 0.0 %".
- **The healing chart is easier to read.** The chart under the boss HP line used to scale to the single biggest second of healing, so one big burst (say 39k when the fight averaged 4.4k) squashed everything else into a flat strip. It now scales to the usual high level of healing (the 95th percentile) and cuts off the few bigger seconds at the top, with a small ▲ over each one. Hover a ▲ to see its time and value. The legend still shows the peak.
- A rare case where an ally's attack could be counted as a heal is now counted as damage.
