# Mock Data

Use this data for prototype screens. It is intentionally simplified and public-safe.

## Mock imported recipe

Source URL:

```text
https://example.com/country-sourdough
```

Detected state:

```text
Bread recipe found
Ready to review as a formula
```

## Formula preview — mathematically consistent

Use this exact sample unless deliberately replacing it with another fully checked formula.

All baker’s percentages below are based on **total flour = 1,000g**. Do not mix total-flour percentages with stage-relative percentages in the same card.

Title:

```text
Country Sourdough
```

Summary:

```text
Total dough: 1,800g
Total flour: 1,000g / 100%
Total water: 780g / 78%
Salt: 20g / 2.0%
Prefermented flour: 200g / 20%
```

Math check:

```text
Total dough = 1,000g flour + 780g water + 20g salt = 1,800g
Hydration = 780 ÷ 1,000 = 78%
Salt = 20 ÷ 1,000 = 2.0%
Prefermented flour = 200 ÷ 1,000 = 20%
```

## Stages

### Levain

Percentages here still use the **overall total-flour basis**, not stage-relative basis.

| Ingredient | Quantity | Baker % | Note |
|---|---:|---:|---|
| Bread flour | 200g | 20% | prefermented flour |
| Water | 200g | 20% | levain water |
| Levain total | 400g | — | prepared component total |

### Final Dough

Final dough rows show **weights only**. Do not show baker’s percentages in the final dough section; the percentages belong in the Overall Formula.

| Ingredient | Quantity | Note |
|---|---:|---|
| Bread flour | 800g | final flour |
| Water | 580g | final water |
| Salt | 20g | salt |
| All levain | 400g | prepared component |

### Overall totals

| Total | Quantity | Baker % |
|---|---:|---:|
| Total flour | 1,000g | 100% |
| Total water | 780g | 78% |
| Total salt | 20g | 2.0% |
| Total dough | 1,800g | — |

## Display rules for formula cards

- Use **one percentage basis** per card: Overall Formula percentages are based on total flour.
- Do not show baker’s percentages in the Final Dough section; final dough is a mixing/build section with weights only.
- Do not show `100%` on levain flour unless the UI explicitly says `stage-relative`.
- Composite rows such as `Levain total` and `All levain` show grams only, not baker’s %.
- Do not show `0g` for unknown component quantities.
- Do not show `1,840g` for this sample.
- Do not include starter seed/inoculation unless its flour/water contribution is explicitly modeled.
- If a parser is uncertain, show an honest review note rather than fake precision.

## Scaling examples

Scale by total dough:

```text
Scale to 2,400g total dough
```

Scale by ingredient constraint:

```text
I have 1,000g bread flour
```

Rebase after mis-weigh:

```text
I added 720g water by mistake
```

## Paywall mock state

```text
Free imports used: 3 of 3
Monthly: £2.99/month
Yearly: £14.99/year
```

## Trust copy options

- No account. Your formulas stay on this iPhone.
- Review before saving. You stay in control.
- Check the numbers before your next bake.
- No ads. No account. No tracking.
