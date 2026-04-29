# Screen Flow

## Target first-run journey

```text
Promise → Start with a recipe → Browser/detection → Formula preview → Save → Scale / Paywall
```

## 1. Promise / first view

Purpose:

- orient the user quickly
- communicate the product in one breath
- avoid a cold empty state
- set up that the first preview is a timed glimpse of a web recipe becoming a formula, not a generic onboarding card

This is the first view a user sees. Use this exact order:

1. Compact `OpenCrumb` identity.
2. Primary message:

> See the formula behind your bread recipes.

3. Supporting message:

> Trust the numbers and scale with confidence.

4. Animated transformation card loop:

```text
web page / recipe text
→ punchy highlight on 200g flour
→ punchy highlight on 200g water
→ punchy highlight on 800g flour
→ punchy highlight on 580g water
→ punchy highlight on 20g salt
→ website/article layer disappears while highlighted quantities remain
→ formula appears around them at a 50/50 transition midpoint
→ highlighted quantities/words move into their matching formula rows
→ derived numbers appear one by one as the highlighted values land
→ formula preview settles
→ transition back and repeat
```

The loop should use two same-size overlaid cards in the same footprint. The source state should feel like a credible clipped web recipe page, with light website/article cues and optionally a subtle bread image/background. Source quantities should highlight in sequence before the formula appears: `200g flour`, `200g water`, `800g flour`, `580g water`, then `20g salt`. Remove the green `Recipe Found` chip completely from this first-view animation. Use a highlight color that pops clearly — warm gold/amber/highlighter yellow preferred — with a deliberate rhythm. After the website/article layer disappears, the highlighted quantities/words should remain. The formula should then transition in around those retained highlights at roughly a 50/50 midpoint, and the highlighted quantities/words should move into their matching formula rows. As the highlighted source values land, derived numbers should appear one by one: total flour `1,000g`, total water `780g`, hydration `78%`, salt `2%`, and total dough `1,800g`. Use `flour`, not `bread flour`, in the visible source/formula labels so the formula terminology stays consistent. The formula state should resolve in-place over the same card footprint, with enough rows to feel like a real worksheet and lower rows allowed to spill/crop beneath the torn edge. Use a slightly bolder, intentionally jagged torn-paper bottom edge so it reads as a glimpse from a longer page. Never leave empty reserved whitespace where the chip used to sit.

5. Compact trust line:

> Source quantities stay visible before you save.

6. Primary CTA:

> Import Your Recipe

Secondary CTA, only if it does not compete:

> Try a Sample Formula

Trust alternative if space is tight:

> No account. Your formulas stay on this iPhone.

The hero tagline and supporting line are mandatory and should remain visible above the fold. Do not substitute weaker tagline copy.

## 2. Start with a real recipe

Purpose:

- push toward the core action
- avoid making the user discover the Browse tab alone

Options:

- Browse recipe sites
- Paste a recipe URL
- Try a sample formula

## 3. Recipe detected

Purpose:

- quietly confirm that OpenCrumb understands the page
- invite preview without overclaiming

Good messages:

- Bread recipe found
- Ready to review as a formula
- Preview Formula

Avoid:

- AI magic language
- noisy banners
- automatic saving

## 4. Formula preview

Purpose:

- deliver the aha moment
- prove that the messy recipe has become a usable structure
- show enough math and stages to build trust
- present a glimpse of conversion, not just a completed formula card

Must feel:

> This is my recipe, but clearer.

Important:

- first-session preview should use a compact infographic-like transformation surface
- show recipe excerpt → extracted structure → formula rows
- preserve source quantities so the math feels checkable
- show baker’s percentages
- show hydration
- show stage structure
- show uncertainty honestly
- never show fabricated `0g` component rows
- include trust language in the preview itself: review before saving, unclear amounts are flagged, no account, no tracking, stays on iPhone

Avoid:

- dumping a finished formula card on screen with no visible conversion story
- replacing the visual proof with generic feature bullets
- AI-magic framing or fake certainty

## 5. Saved formula

Purpose:

- confirm persistence
- route to practical next action

Next actions:

- Scale this formula
- Edit formula
- Import another recipe

## 6. Paywall

Purpose:

- monetize after trust
- explain continuation clearly

Appears after:

- free imports are used
- user understands recipe → formula value

Copy:

> Keep turning recipes into formulas.

Benefits:

- Import bread recipes
- Save unlimited formulas
- Scale with baker’s percentages
- Keep everything organized on your iPhone
