# Aion2DPSMeter 0.15.2

# Aion2DPSMeter 0.15.2

Your saved settings now apply from the start, and the party inspector opens and looks players up when it should.

- **Settings that were ignored until you changed them.** When the meter starts, the overlay sends your saved settings to the core. Some of them arrived while the meter was still starting and were lost, so the core kept its defaults for the whole session: hide in game menus and its capture method, the inspector's automatic open and lookup, abysslogs ranks, "Boss fights only", "Show in taskbar" and idle hide. That is why menu detection sometimes needed a toggle to work, and why the inspector rarely opened by itself. These settings are now sent again until the meter is ready.
- **The inspector opens when you join a party** (new default; Settings → Party → "Open when you join a party"). If you changed that setting before, check it once.
- **Opening the inspector looks everyone up.** When you open it yourself, every listed applicant and member without a lookup yet is looked up on the official armory; no more clicking each card.
- **An applicant who arrives right after you closed the inspector** is held back for 20 s as before, but now opens it when they apply again. Before, they stayed hidden for 30 minutes.
