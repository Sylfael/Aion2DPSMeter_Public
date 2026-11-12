# Aion2DPSMeter 0.23.1

# Aion2DPSMeter 0.23.1

Fixes from the first day on 0.23.0. Nothing new.

- **A freeze fixed.** The meter could lock up for good when a window was closed or opened right after a window had been moved or resized. Every window open and close now also leaves a line in the log, and the log says when the meter stops answering, so a freeze that still happens can be traced.
- **Clearer hit rates in Fight details.** Theostone ticks count as hits, and as they never crit or land from the back or the front, they lower every total rate a little. The hits tile now says how many of the hits are theostone ticks, and the rate tooltips also give each rate without them. No number changed.
