# Current Rork Task — First-Session Trust Glimpse

Paste/use this as the next Rork Max instruction after connecting this repo.

## Objective

Redesign OpenCrumb’s first-session formula preview / aha moment so it feels like a **glimpse** of a written bread recipe being turned into a trustworthy baker’s formula.

This is the highest-priority screen. Do not broaden the product.

## Required reading before changing screens

Read these files in this repo first:

- `RORK_PROMPT.md`
- `PRODUCT_BRIEF.md`
- `SCREEN_FLOW.md`
- `GUARDRAILS.md`
- `MOCK_DATA.md`
- `BBGA_FORMULA_FORMAT.md`
- `HAMELMAN_FORMULA_HERO.md`
- `RORK_WORKFLOW.md`

## Product truth

OpenCrumb is an iPhone-only SwiftUI app for serious home bakers.

It turns messy bread recipes into organized, scalable baker’s-percentage formulas.

The R1.0 loop is deliberately narrow:

```text
Import → Formula → Scale
```

The aha moment is:

> My real recipe just became an organized, believable formula I might trust for my next bake.

## What to build / revise

Create or revise the first view / first-session preview so one glance communicates:

```text
web recipe page → Recipe Found → formula preview
```

This should be a compact, native SwiftUI, infographic-like transformation surface that can sit on the promise screen itself.

Do **not** show only a finished formula card dumped on screen. The user needs to see why the result is trustworthy.

## First-view hierarchy that must be enforced

The first view should not open with a generic carousel, empty state, or finished formula card.

Use this order:

1. Compact `OpenCrumb` identity.
2. Exact hero tagline:

   > See the formula behind your bread recipes.

3. Exact supporting line:

   > Trust the numbers and scale with confidence.

4. The animated transformation card loop described below.
5. One compact trust line, for example:

   > Source quantities stay visible before you save.

6. Primary CTA:

   > Import Your Recipe

The tagline and supporting line are not optional decoration. They must be visible above the fold and must not be replaced by vaguer copy like “Bring baker’s maths to your recipes.”

## Visual direction

Use a calm, serious-baker visual metaphor built around **two same-size cards occupying the same footprint**:

1. **Website recipe card**
   - looks like a credible clipped website recipe/article page, not a generic white text card
   - same width/height as the formula card
   - include source quantities visibly
   - should feel like the written document the baker started with
   - use light website/article cues: source domain, tiny masthead/browser bar, serif article title, short dek, paragraphs, ingredient quantities, and optionally a subtle bread/crumb image or warm photo block
   - visible ingredient labels should use `flour`, not `bread flour`, so the source and formula terminology stay consistent
   - improve realism without making the card busy; the user should read “real recipe page” instantly
   - bottom edge should be subtly ragged / torn-paper style so it feels like a glimpse from a longer page, not a complete document

2. **Formula card**
   - same width/height as the website recipe card
   - aligned exactly over the same card footprint
   - clean formula rows with weights and baker’s percentages
   - show enough rows that the formula feels like a real worksheet, not a tiny summary card
   - allow lower formula rows to continue past / crop under the torn-paper bottom edge so it feels like there is more formula below the clipped page
   - keep the top rows legible; only lower rows should be partially cut off
   - visually the payoff, but still connected to the source
   - can share the same ragged/torn bottom edge treatment if it reinforces the “glimpse” idea

3. **Transition / overlay idea**
   - run the overlay in a restrained timed loop, not as a one-off static mock
   - suggested loop: web page / recipe text settles in → source quantities highlight in sequence (`200g flour`, then `200g water`, then `800g flour`) → real `Recipe Found` chip appears → formula preview resolves in-place → animated transition back to the web page state → repeat
   - the quantity highlights should feel like OpenCrumb is finding the ingredients in the source page before resolving the formula; use restrained warm highlight marks, not neon scan effects
   - use a crossfade, vertical wipe, peel/reveal, or stacked overlay where the formula appears in-place over the original recipe text
   - avoid side-by-side comparison if it makes the screen feel like a diagram; the stronger idea is **same card, transformed**
   - keep motion restrained and Apple-like
   - the loop can later grow to include camera/import states, but for now keep the first loop focused on web page → recipe found → formula preview

4. **Detection layer**
   - use the real OpenCrumb browser detection chip styling, not a newly invented mock chip
   - production reference: `DSRecipeDetectedChip` in `OpenCrumb/Shared/DesignSystem/Components/DSRecipeDetectedChip.swift`
   - match the real chip semantics: `Recipe Found`, `checkmark.circle.fill`, white text/icon, capsule filled with OpenCrumb success green (`Color.ocSuccess` / `#16A34A`), horizontal padding around `.ocSpace5`, vertical padding around `.ocSpace3`, and a soft shadow similar to `Color.black.opacity(0.25), radius: 8, y: 4`
   - if the source recipe title is shown in the chip, use the real two-line style: small `Recipe Found` label over the recipe title; otherwise use the single-line chip
   - no extra `Tap to inspect`, pointer, cursor, or fake tap chip is needed — the real detection chip already carries the affordance
   - the chip should behave as an overlay badge, not as reserved layout space inside the card; do not leave a blank band where the chip used to be after it moves or fades
   - when the chip is not visible, article/formula content should use the available vertical space naturally
   - examples of understated extraction states, if shown elsewhere: “flour found”, “water found”, “levain stage detected”, “review needed”
   - no AI magic language

5. **Depth and finish**
   - use tasteful drop shadows and subtle gradients; they are cheap and effective here
   - recipe/formula card should have a soft raised-paper shadow so it feels physically lifted from the page
   - use a gentle warm paper gradient on the card surface rather than flat white if it improves the editorial feel
   - background can use a restrained warm-to-cream gradient, but avoid glossy SaaS glassmorphism
   - formula rows or summary chips may use very light gradient/tint accents for hierarchy
   - keep contrast and legibility high; gradients must never reduce readability of formula numbers

6. **Ragged bottom edge**
   - make the bottom torn-paper edge slightly bolder and more intentionally jagged than a tiny decorative ripple
   - it should read as a clipped glimpse from a longer web recipe page
   - keep it tasteful and paper-like, not cartoonish or Halloween-style

## Trust copy that must be visible

Include trust messaging in the preview itself, not hidden in a footer or later screen:

- Source quantities stay visible
- Review every number before saving
- Unclear amounts are flagged, not guessed
- No account. No tracking. Your formulas stay on this iPhone.

Use serious, restrained language.

## Formula rules

Visible formula data must remain mathematically plausible and consistent with the mock data:

- Overall Formula uses total-flour baker’s percentages.
- Levain Build uses build percentages and may show `Levain total 400g 200%`.
- Final Dough uses weights only.
- Use `Flour`, not a conflicting `Bread flour` label.
- Do not show impossible `0g` component rows.
- Do not invent fake precision.
- Do not double-count levain.

## Design feel

The screen should feel:

- calm
- precise
- native iPhone
- trustworthy
- useful rather than decorative
- professional enough for serious home bakers

It should not feel like:

- AI chat
- generic recipe manager
- meal planner
- SaaS dashboard
- neon AI app
- marketing carousel with hollow feature bullets

## Interaction guidance

Prefer a simple transition or progressive reveal:

- source excerpt settles in
- extraction/check states appear subtly
- formula rows resolve into place

Keep motion restrained and Apple-like. No magic wand / sparkle gimmick.

## Primary CTA

Use:

> Save Formula

Secondary:

> Edit Before Saving

Small support copy:

> Check the numbers before your next bake.

## Acceptance checklist

The result is acceptable only if a serious baker can look at the screen and immediately understand:

- this started as written recipe prose
- OpenCrumb extracted structure from it
- the output is a baker’s formula
- the user can review before saving
- questionable amounts are not guessed
- the app is local-first/no-account/no-tracking

If any of those are missing, revise before stopping.
