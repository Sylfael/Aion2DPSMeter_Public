# Aion2DPSMeter 0.24.1

# Aion2DPSMeter 0.24.1

A smoother meter. No new feature and no change to any number.

- **Turning "Game FPS" off no longer freezes the windows.** It could hold every window for up to a second.
- **Closing a side window or changing a setting no longer waits for the disk.** Window positions and settings are now written in the background, within two seconds. If the meter is killed or crashes in the two seconds after you close a window, that window's last position is not kept.
- **Lighter during long fights.** The live numbers are now kept up to date hit by hit instead of being recounted from the whole fight four times a second. The gain is largest in long fights with many players. The numbers are the same as in 0.24.0: this was checked on every recorded session.
- **Fight details and hidden windows do less work.** A finished fight is prepared once instead of every second, and the Party and Settings windows do nothing while they are hidden.
- After turning "Game FPS" off and on again quickly, the bar can read "off" for a few seconds before the frame rate comes back.
