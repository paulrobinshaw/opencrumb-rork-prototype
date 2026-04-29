# Rork Max Prompt

I’m building OpenCrumb, an iPhone-only SwiftUI app for serious home bakers.

Please create a polished, native-feeling SwiftUI prototype / implementation direction for OpenCrumb’s final launch experience. The goal is not to invent a new app. The goal is to make the existing product feel clear, trustworthy, App Store-ready, and emotionally compelling in the first session.

Use this repo as prototype context only. Do not assume this is the production app. Use mock data and prototype screens.

Before creating any formula card, read `MOCK_DATA.md`, `BBGA_FORMULA_FORMAT.md`, and `HAMELMAN_FORMULA_HERO.md`. Formula cards must be mathematically correct: one baker’s percentage basis, no mixed stage-relative percentages, no double-counting levain, and no fake precision. The formula table should be the hero, not a small decorative proof card.

## Product summary

OpenCrumb turns messy bread recipes into organized, scalable baker’s-percentage formulas.

The target user is a serious home baker or small-batch baker who repeats doughs, scales recipes, uses preferments/levains/soakers, and wants numbers they can trust for the next bake.

The core R1.0 loop is:

1. Import a real bread recipe through an in-app browser.
2. Detect that the page contains a recipe.
3. Show a preview where the messy recipe becomes a believable structured formula.
4. Let the baker review/save it.
5. Let the baker scale the formula confidently using baker’s percentages.

The core emotional aha moment is:

> My real recipe just became an organized, believable formula I might trust for my next bake.

The app should feel calm, precise, legible, practical, and native to iPhone. It should not feel like a generic AI wrapper, meal planner, recipe scrapbook, or SaaS dashboard.

## Prototype target

Create a polished native SwiftUI prototype of this first-run flow:

1. Promise screen
2. Start/import choice
3. Browser recipe detected state
4. Formula preview / aha screen
5. Saved formula screen
6. Paywall after free imports

Prioritize:

1. Clarity of first session
2. Trust in the formula preview
3. Native Apple feel
4. Screenshot-worthy surfaces
5. Calm subscription ask after value

## Screen 1 — Promise

Goal: Explain OpenCrumb in one breath.

Suggested headline:

> Turn bread recipes into formulas you can trust.

Supporting bullets:

- Import a recipe
- Check the baker’s percentages
- Scale the dough with confidence

Primary CTA:

> Import a Recipe

Secondary CTA:

> Try a Sample Formula

Trust line:

> No account. Your formulas stay on this iPhone.

## Screen 2 — Start with a real recipe

Goal: Move the user straight into the import aha.

Copy direction:

> OpenCrumb works best when you start with a recipe you already bake.

Options:

- Browse recipe sites
- Paste a recipe URL
- Try a sample formula

Primary behavior:

The user should be taken into the Browse tab / browser flow, not left to discover it alone.

## Screen 3 — Recipe detected

When a recipe page is detected, show a calm, confident detection chip or bottom card.

Avoid:

> AI found a recipe!

Prefer:

> Bread recipe found
> Ready to review as a formula
> Preview Formula

CTA:

> Preview Formula

Secondary:

> Keep Browsing

Trust line:

> Review before saving. You stay in control.

## Screen 4 — Formula preview / aha

This is the most important screen.

It should show the imported recipe transformed into a structured baking formula.

Must show:

- recipe/formula title
- total dough weight if known
- hydration if known
- ingredient rows
- baker’s percentages
- stages if present, e.g. Levain, Final Dough, Soaker
- source quantities where useful
- warnings or uncertainty honestly

Critical trust rule:

Never show fabricated certainty. If the parser does not know a component quantity, do not show “0g levain” or “0g tangzhong.” Use honest labels like:

- prepared levain
- quantity from stage
- review amount
- blank quantity with a review note

The preview should feel like:

> This is my recipe, but clearer.

Primary CTA:

> Save Formula

Secondary:

> Edit Before Saving

Small trust copy:

> Check the numbers before your next bake.

## Screen 5 — Post-save

After saving, show a success transition into the actual formula.

Message:

> Saved as a formula

Next actions:

- Scale this formula
- Edit formula
- Import another recipe

## Screen 6 — Paywall

Business model:

- 3 free imports
- £2.99/month
- £14.99/year

Paywall should:

- come after value is understood
- be calm and honest
- avoid manipulative urgency
- explain what subscription supports

Suggested headline:

> Keep turning recipes into formulas.

Supporting copy:

> You’ve used your free imports. Subscribe to keep importing recipes and building your baking formula library.

Benefits:

- Import bread recipes
- Save unlimited formulas
- Scale with baker’s percentages
- Keep everything organized on your iPhone

Trust copy:

> No ads. No account. No tracking.

CTA:

> Continue

Secondary:

> Not now

Only include “Not now” if designing a soft paywall variant.

## Formula screen requirements

A formula detail screen should emphasize:

- formula title
- total dough weight
- hydration
- baker’s percentage table
- ingredient quantities
- stages/components
- scaling action

Rows should make quantities and baker’s percentages easy to scan. Numeric data should be more visually structured than prose. Use monospaced digits if appropriate.

## Scaling experience

Scaling should feel like the practical payoff.

Support three mental models:

- Scale to total dough weight
- Scale to available ingredient
- Recalculate after mis-weigh

Examples:

- Scale to 2400g total dough
- Scale because I have 1000g flour
- I added 720g water by mistake; recalculate

Suggested copy:

> Scale without changing the formula.

## App Store screenshot-worthy story

The product should be visually strong enough to support these App Store screenshot messages:

1. Turn recipes into formulas
2. Scale any batch
3. Review before saving
4. Built for bread
5. No account required

Avoid screenshot promises about production planning, timers, backplanning, or attention queues for R1.0.

## Technical constraints

If generating SwiftUI code:

- Use native SwiftUI.
- iPhone-first layouts.
- No backend assumptions.
- No CloudKit.
- No account/login flow.
- No AI chat UI.
- No generic dashboard.
- Keep business logic separate from UI.
- Do not invent untested scaling math.
- Use placeholder/mock data only.
- Make UI accessible.
- Icon-only controls need labels.
- Avoid tiny text.
- Avoid shrinking fonts to fit long text. Prefer abbreviating labels, wrapping, or simplifying copy.

## Do not do these things

Do not:

- Reposition OpenCrumb as a recipe manager
- Lead with AI as the identity
- Add social/community features
- Add accounts
- Add meal planning
- Add nutrition tracking
- Add grocery lists
- Add production scheduling for R1.0
- Add chat
- Add Android/cross-platform language
- Use fake testimonials
- Make the app look like a generic SaaS dashboard
- Hide uncertainty in import results
- Show impossible precision
- Invent features beyond Import → Formula → Scale

The final result should make a serious home baker think:

> This understands how I bake. I could trust this with my next dough.
