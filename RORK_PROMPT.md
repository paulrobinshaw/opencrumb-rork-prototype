# Rork Max Prompt

I’m building OpenCrumb, an iPhone-only SwiftUI app for serious home bakers.

Please create a polished, native-feeling SwiftUI prototype / implementation direction for OpenCrumb’s final launch experience. The goal is not to invent a new app. The goal is to make the existing product feel clear, trustworthy, App Store-ready, and emotionally compelling in the first session.

Use this repo as prototype context only. Do not assume this is the production app. Use mock data and prototype screens.

Before creating any formula card, read `MOCK_DATA.md`, `BBGA_FORMULA_FORMAT.md`, and `HAMELMAN_FORMULA_HERO.md`. Formula cards must be mathematically correct: Overall Formula uses total-flour baker’s %, Levain Build uses clearly labelled build %, Final Dough uses weights only, no double-counting levain, and no fake precision. The formula table should be the hero, not a small decorative proof card.

## Product summary

OpenCrumb extracts the formula behind trusted bread recipes so bakers can review the numbers and scale with confidence.

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

Goal: Explain OpenCrumb in one breath and immediately show the import-to-formula promise.

This is the first view a user sees. It must not be a generic marketing carousel or empty state.

Enforced vertical order:

1. Compact `OpenCrumb` identity.
2. Exact headline:

> See the formula behind your bread recipes.

3. Exact supporting line:

> Trust the numbers and scale with confidence.

4. Animated transformation card loop:

```text
web recipe page / recipe text → Recipe Found chip → formula preview → transition back → repeat
```

5. One compact trust line:

> Source quantities stay visible before you save.

6. Primary CTA:

> Import Your Recipe

Secondary CTA, only if there is room and it does not compete:

> Try a Sample Formula

Trust line alternative:

> No account. Your formulas stay on this iPhone.

The hero tagline and supporting line are mandatory. Do not replace them with softer or vaguer copy such as “Bring baker’s maths to your recipes.”

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

### Critical first-session direction: this must be a glimpse, not a dumped card

Do not make the first preview feel like a finished formula card dropped onto the screen with supporting copy underneath. The first-session visual should communicate, at a glance, that OpenCrumb took written bread-recipe prose and turned it into a professional baker's formula the user can review.

Use a compact infographic-like transformation surface, native to SwiftUI and calm in tone:

- written recipe excerpt
- extracted structure / parsing checks
- professional formula rows

Think:

> written recipe -> extracted structure -> professional formula

The formula table is still the eventual hero, but the onboarding aha should visually show the conversion from prose to formula, not just the end state.

This should feel like a glimpse of the promise, not a full workflow lecture. One glance should communicate:

> My recipe prose became a structured formula I can verify.

Suggested microcopy for this transformation surface:

- From recipe prose to baker's formula
- Source quantities stay visible
- Review every number before saving
- Unclear amounts are flagged, not guessed
- No account. No tracking. Your formulas stay on this iPhone.

Visual metaphor direction:

- use two same-size cards occupying the same footprint: a website recipe-text card and a formula card
- run the same-footprint cards as a restrained timed loop, not a static before/after graphic
- the loop should read: web page / recipe text settles in → real `Recipe Found` chip appears → formula preview resolves in-place → animated transition back to the web page state → repeat
- the website card transitions into the formula card in-place using a restrained crossfade, wipe, peel, or overlay reveal
- the cards should feel exactly aligned, not like two unrelated panels
- the bottom edge should be slightly bolder and more intentionally jagged / torn-paper style so the user reads it as a clipped glimpse from a longer recipe document; keep it tasteful and paper-like, not cartoonish
- use the real OpenCrumb `DSRecipeDetectedChip` styling rather than inventing a new chip: `Recipe Found`, `checkmark.circle.fill`, white text/icon, `Color.ocSuccess` (`#16A34A`) capsule, soft shadow
- no extra `Tap to inspect`, pointer, cursor, or fake tap chip is needed
- source state: clipped web page / recipe text excerpt from a real bread recipe with source quantities visible
- transformed state: clean formula rows with weights and baker's percentages
- add tasteful depth: soft card drop shadows, a gentle warm paper gradient, and subtle background gradients are encouraged if they improve polish without reducing legibility
- the loop can later include camera/paste/import variants, but do not broaden the current first view unless explicitly asked

Avoid:

- a full-screen formula card with no visible source context
- generic feature bullets replacing the actual preview
- hype language about AI
- chat UI
- neon sparkle / magic-wand visuals
- glossy SaaS glassmorphism or gradients that overpower the baking-paper feel
- implying the app autogenerates perfect math without review

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

Trust must be visible in the preview itself, not relegated to secondary marketing copy. The screen should explicitly reinforce:

- review before saving
- source quantities retained
- uncertainty flagged instead of guessed
- math is checkable
- no account
- local-first / stays on this iPhone
- no tracking

Use serious-baker language. This is not "AI magic." It is recipe interpretation presented with restraint and checkable math.

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
