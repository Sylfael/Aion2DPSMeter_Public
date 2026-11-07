# Aion2DPSMeter 0.14.1

# Aion2DPSMeter 0.14.1

Fixes the crash at start in 0.14.0.

- **0.14.0 could crash right after starting** with "state() called before manage()". The overlay asked for the new hide/show hotkey before the meter had finished starting. The meter now waits for itself. If 0.14.0 crashes for you, download this version from the releases page and unzip it over the old one; your settings and fights are kept.
