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

The Overall Formula uses total-flour baker’s percentages. The Levain Build uses clearly labelled build-relative percentages. The Final Dough uses weights only.

Title:

```text
Country Sourdough
```

Summary:

```text
Total dough: 1,800g
Flour: 1,000g / 100%
Water: 780g / 78%
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

### Levain Build

Levain Build uses **build-relative percentages**. In this 100% hydration levain, levain flour is 100%, levain water is 100%, and levain total is 200%.

| Ingredient | Quantity | Build % | Note |
|---|---:|---:|---|
| Flour | 200g | 100% | levain flour; 20% of total formula flour |
| Water | 200g | 100% | levain water |
| Levain total | 400g | 200% | prepared component total |

### Final Dough

Final dough rows show **weights only**. Do not show baker’s percentages in the final dough section; the percentages belong in the Overall Formula.

| Ingredient | Quantity | Note |
|---|---:|---|
| Flour | 800g | final flour |
| Water | 580g | final water |
| Salt | 20g | salt |
| All levain | 400g | prepared component |

### Total

| Total | Quantity | Baker % |
|---|---:|---:|
| Flour | 1,000g | 100% |
| Water | 780g | 78% |
| Salt | 20g | 2.0% |
| Total dough | 1,800g | 180% |

## Display rules for formula cards

- Label percentage bases clearly: Overall Formula uses total-flour baker’s %, while Levain Build uses build-relative %.
- Do not show baker’s percentages in the Final Dough section; final dough is a mixing/build section with weights only.
- Levain Build may use `100%` on levain flour and water when the column is clearly labelled `Build %`.
- Levain total shows its build total percentage (`200%` in this sample). `All levain` in Final Dough shows weight only, no percentage.
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
I have 1,000g flour
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
