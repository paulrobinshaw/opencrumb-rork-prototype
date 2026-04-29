# BBGA-style Formula Format

This is a public-safe guide for Rork prototypes. Treat it as **BBGA-style / professional bread formula layout**, not an official BBGA standard document.

The goal is to keep OpenCrumb formula previews mathematically credible for serious bakers.

## Core idea

Professional bread formulas often separate a bread into:

1. **Overall Formula** — the complete formula totals for the whole dough.
2. **Pre-ferment / Levain Build** — ingredients mixed ahead of time.
3. **Final Dough** — ingredients added at final mix, including the prepared levain/pre-ferment as a component.

OpenCrumb’s preview card should make this structure clear without double-counting ingredients.

## Baker’s percentage basis

Unless explicitly labelled otherwise, baker’s percentages use **total flour = 100%**.

Example:

```text
Total flour = 1,000g = 100%
Total water = 780g = 78%
Salt = 20g = 2.0%
```

Hydration:

```text
hydration = total water ÷ total flour
780 ÷ 1,000 = 78%
```

Salt percentage:

```text
salt % = salt ÷ total flour
20 ÷ 1,000 = 2.0%
```

## Prefermented flour vs preferment mass

Do not confuse:

- **Prefermented flour %** — flour inside the levain/pre-ferment as a percentage of total flour.
- **Preferment mass** — the total weight of the prepared levain/pre-ferment, including flour + water, and maybe seed/starter if explicitly modeled.

Example:

```text
Total flour = 1,000g
Levain flour = 200g
Prefermented flour = 200 ÷ 1,000 = 20%
```

If the levain is 100% hydration:

```text
Levain flour = 200g
Levain water = 200g
Levain total = 400g
```

So:

```text
Prefermented flour = 20%
Levain total mass = 400g
```

Those are not the same number and should not be displayed as if they are.

## Safe compact sample for OpenCrumb

Use this exact sample for prototype cards unless replacing it with another checked formula.

### Overall Formula

| Ingredient | Quantity | Baker % |
|---|---:|---:|
| Total flour | 1,000g | 100% |
| Total water | 780g | 78% |
| Salt | 20g | 2.0% |
| Total dough | 1,800g | — |

Top metrics:

```text
Hydration: 78%
Salt: 2.0%
Prefermented flour: 20%
Total dough: 1,800g
```

### Levain Build

Percentages below still use **overall total flour basis**, not stage-relative basis.

| Ingredient | Quantity | Baker % | Note |
|---|---:|---:|---|
| Bread flour | 200g | 20% | prefermented flour |
| Water | 200g | 20% | levain water |
| Levain total | 400g | — | component total |

### Final Dough

Final dough is the mixing/build section. Show weights only here; do **not** show baker’s percentages in the Final Dough table.

| Ingredient | Quantity | Note |
|---|---:|---|
| Bread flour | 800g | final flour |
| Water | 580g | final water |
| Salt | 20g | salt |
| All levain | 400g | prepared component |

Check:

```text
Flour: 200g levain flour + 800g final flour = 1,000g
Water: 200g levain water + 580g final water = 780g
Salt: 20g
Total dough: 1,000g + 780g + 20g = 1,800g
```

## Display rules

### Rule 1 — one percentage basis per compact card

Overall Formula is where baker’s percentages belong:

```text
OVERALL FORMULA
Flour 1,000g 100%
Water   780g  78%
Salt     20g 2.0%
```

The Final Dough section should show weights only:

```text
FINAL DOUGH
Bread flour 800g
Water       580g
Salt         20g
All levain  400g
```

Do **not** put baker’s percentages in Final Dough rows. That makes the display look like it is mixing formula percentage logic with mixing-stage instructions.

### Rule 2 — component totals usually have no baker’s %

These rows should show weight only:

```text
Levain total 400g —
All levain 400g —
```

Do not invent a baker’s percentage for `All levain` in a compact preview.

### Rule 3 — avoid double-counting levain

In the final dough, `All levain 400g` is a prepared component added to the bowl.

Its flour and water are already included in the overall formula totals. Do not add levain flour/water again when calculating total flour/water.

### Rule 4 — omit seed/starter unless modeled

A production formula may include seed/starter/inoculation. But for a compact onboarding card, omit it unless the flour/water contribution is explicitly modeled.

Do not quietly add starter seed and then show a total dough value that does not reconcile.

### Rule 5 — uncertainty beats fake precision

If imported recipe data is incomplete, show review language instead of fake numbers:

- `review amount`
- `prepared component`
- `quantity from levain build`
- blank quantity with a warning

Never show `0g levain`, `0g tangzhong`, or a mathematically impossible total.

## What Rork should optimize for

Formula cards should look credible before they look decorative.

A serious baker should be able to glance at the card and see:

- total flour basis
- hydration
- salt percentage
- prefermented flour percentage
- levain/final dough split
- no double-counting
- no baker’s percentages in the Final Dough section

If a card cannot show all of that clearly, simplify it rather than making up numbers.
