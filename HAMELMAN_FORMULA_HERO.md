# Hamelman-style Formula Hero

Use this when Rork is designing OpenCrumb’s first-run / aha screen.

The goal is to make the formula itself the proof.

OpenCrumb should not feel like a landing page with a decorative formula card. It should feel like a serious bread formula tool that happens to be approachable on iPhone.

## Design principle

Think **Jeffrey Hamelman / professional bread formula sheet**, adapted to iPhone.

The screen hierarchy should be:

1. Formula table / proof
2. Short promise
3. Action button

Not:

1. Marketing headline
2. Paragraph
3. Small decorative card

## What the hero should communicate instantly

A serious baker should see, within 2 seconds:

- this is a formula, not a recipe scrapbook
- the baker’s percentage basis is explicit
- hydration and salt are anchored to total flour
- levain/pre-ferment is separated from final dough
- levain is not double-counted
- the numbers reconcile
- the app understands bread structure

## Preferred screen structure

### Top microcopy

Keep this short:

```text
Recipe → Formula
```

or:

```text
Your recipe, structured as a baker’s formula.
```

Avoid a long marketing paragraph above the card.

### Main hero card

The card should take most of the screen.

Recommended order:

1. Formula title
2. Basis line
3. Overall Formula
4. Levain Build
5. Final Dough
6. Totals / checks

Example header:

```text
Country Sourdough
Total flour basis: 1,000g = 100%
```

### Overall Formula

Show the total dough percentage. This is the yield from flour: 100% flour + 78% water + 2% salt = 180% total dough.

```text
OVERALL FORMULA
Flour          1,000g   100%
Water            780g    78%
Salt              20g   2.0%
Total dough    1,800g   180%
```

### Levain Build

Levain Build uses build-relative percentages. For this 100% hydration levain, flour is 100%, water is 100%, and levain total is 200%.

```text
LEVAIN BUILD
Flour      200g   100%
Water            200g   100%
Levain total     400g   200%
```

### Final Dough

Final dough should be weights only. Do not show baker’s percentages in this section.

```text
FINAL DOUGH
Flour      800g
Water            580g
Salt              20g
All levain       400g
```

### Check line

Include one small reconciliation line if there is room:

```text
Flour 1,000g · Water 780g · Salt 20g · Dough 1,800g
```

or:

```text
Levain flour/water included in totals — not double-counted.
```

## Visual treatment

The formula table is the visual hero.

Use:

- compact professional rows
- aligned numbers
- monospaced digits
- clear section labels
- low ornamentation
- enough contrast for numeric scanning
- table/card occupying the central vertical space

Avoid:

- oversized marketing headline pushing the card down
- tiny formula card
- badges replacing a real table
- decorative bread imagery
- lifestyle copy
- recipe-manager language
- vague “organized recipes” phrasing

## CTA placement

Primary CTA can sit below the formula card:

```text
Import a Recipe
```

Secondary:

```text
See Sample Conversion
```

Trust line:

```text
No account. Preview before saving.
```

## Formula correctness rules

Use the exact checked sample from `MOCK_DATA.md`.

Never show:

```text
Total dough 1,840g
Levain flour 100g 100%
All levain with a baker’s % in Final Dough
Final Dough percentages
```

Always make the basis explicit:

```text
Total flour basis: 1,000g = 100%
```

## Why this matters

OpenCrumb’s aha is not “nice onboarding.”

The aha is:

> A real recipe becomes a professional formula I can inspect, trust, and scale.

So the first screen should shout the formula, not the brand promise.
