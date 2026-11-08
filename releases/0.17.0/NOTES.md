# Aion2DPSMeter 0.17.0

# Aion2DPSMeter 0.17.0

The party and applicant inspector, redesigned for a quick "take them or not".

- **Compact rows instead of cards.** Each applicant or member is one row: class, name, combat power and how it compares with your party's average, gear, abysslogs rank for this dungeon, and the verdict. Memo, Block / Trust and links fold away (✎ opens the memo). Long names are cut with "…" and shown in full on hover.
- **Your party at a glance.** A bar on top shows the slots (open ones dashed), the roles (amber when you have no tank or no healer), and the party's combat power range and average. Applicants say what they would fill ("fills healer", "2nd dps").
- **Honest verdicts.** The badge reads *not checked*, *no flags*, *check* or *fail*: never a green pass on no evidence, and never on yourself. Settings → Party → "Fail below CP" / "Check below CP" sets the rule.
- **Applicants in a calm order.** Soonest to expire first (or sort by combat power, abysslogs rank or newest). An application that ends stays a few seconds as a dimmed row, and the list does not move while your mouse is over it.
- **"Look up all".** One button looks up everyone listed (failed lookups are retried). Rows show "looking up · 2 ahead" while the queue runs.
- **How fresh the party list is.** The room line shows its age ("list 8 s ago"), and members say "not on your map" or "no HP update 1 min+" when the game stops telling us about them.
- **Plain error messages**, grade chips in grade order, and "hide" (×) instead of "Dismiss": hiding an applicant here does not decline them in the game.
- **Export and import your memos and lists** (Settings → Party): a file in `Documents\Aion2DPSMeter\`, merged on import.
