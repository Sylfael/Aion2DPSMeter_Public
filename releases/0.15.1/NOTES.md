# Aion2DPSMeter 0.15.1

# Aion2DPSMeter 0.15.1

Two fixes and a small addition.

- **Death count on the "dead" tag.** A player who died more than once in the fight shows "dead ×2", "dead ×3"… instead of just "dead".
- **Boss fight timer fixed when someone tagged the boss first.** If another player hit a boss and ran, and it reset, the meter timed the fight from that hit, so your party's DPS read far too low (2:17 instead of 0:56 on Judge Urahum). Such a tag is no longer a fight: the clock starts at the real pull. Damage and shares were already right.
- **Hide in game menus:** a loading screen no longer switches the capture to the screen copy for the rest of the session (it takes 30 s of black frames now, not 5 s).
