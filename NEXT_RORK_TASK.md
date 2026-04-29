# Next Rork Task — Polish the App Around the Locked First View

## Status

The first-view hero direction is strong enough to pause iteration for now.

Do **not** keep redesigning the first view unless explicitly asked. Treat it as the visual benchmark for the rest of the prototype.

The locked first-view idea is:

```text
credible recipe web page
→ source quantities highlight in rhythm
→ website fades away while highlighted quantities remain
→ formula structure appears around them
→ highlighted quantities land in matching formula rows
→ derived numbers appear one by one
→ formula preview settles
```

This communicates OpenCrumb’s trust promise:

> The formula is traceable back to the source recipe quantities.

## Next objective

Bring the rest of the first-run app experience up to the same level of polish and clarity.

Prioritize these screens in order:

1. **Formula preview / review screen**
   - This is the real product aha after import.
   - It should feel like the expanded, inspectable version of the first-view hero.
   - Show source quantities, formula rows, derived totals, and review states clearly.
   - Preserve the same warm, serious-baker design language.

2. **Saved formula screen**
   - Show that the formula has become a useful working document.
   - Emphasize title, total dough, hydration, formula rows, stages, and next action.
   - Primary next action should be scaling.

3. **Scaling screen**
   - Make the practical payoff obvious.
   - Scaling should feel calm, numeric, and trustworthy.
   - Avoid making it look like a generic calculator.

4. **Paywall after value**
   - Only after the user understands import → formula → scale.
   - Calm, honest, no manipulative urgency.
   - Mention 3 free imports, then £2.99/month or £14.99/year.

## Design continuity requirements

The rest of the prototype should inherit from the first-view direction:

- warm paper / cream background
- precise, serious-baker tone
- strong but restrained typography
- soft shadows and subtle depth
- formula data as the hero
- source quantities and derived numbers shown as traceable
- no AI magic language
- no chat UI
- no generic recipe-manager clutter

## Formula correctness rules

Visible formula data must remain mathematically plausible:

- Overall Formula uses total-flour baker’s percentages.
- Levain Build uses build percentages and may show `Levain total 400g 200%`.
- Final Dough uses weights only.
- Use `Flour`, not `Bread flour`.
- Do not show impossible `0g` component rows.
- Do not invent fake precision.
- Do not double-count levain.

## Acceptance criteria

The next Rork pass is successful if the rest of the prototype feels like it belongs to the same app as the first-view hero, and a serious baker can understand:

- where the formula came from
- which source quantities were used
- what numbers are derived
- what needs review
- how to save and scale the formula
- why the subscription comes after value

Do not broaden the product. Stay inside:

```text
Import → Formula → Scale
```
