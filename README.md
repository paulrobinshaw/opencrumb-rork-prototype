# OpenCrumb Rork Prototype

A stripped public prototype brief for exploring OpenCrumb UI/UX ideas in Rork Max.

This is **not** the production OpenCrumb repo.

Use this repo to prototype:

- first-run onboarding
- browser recipe detection
- import-to-formula preview, especially the first-session glimpse of recipe prose becoming a trustworthy formula
- formula detail polish
- scaling UI concepts
- paywall timing and copy
- App Store screenshot-worthy mock states

Do **not** use this repo for production implementation, data models, import parsing, StoreKit, SwiftData migrations, AIProxy/Gemini configuration, or tested formula math.

Before creating any formula preview, read [`BBGA_FORMULA_FORMAT.md`](BBGA_FORMULA_FORMAT.md), [`HAMELMAN_FORMULA_HERO.md`](HAMELMAN_FORMULA_HERO.md), and [`MOCK_DATA.md`](MOCK_DATA.md). Visible formula cards must be mathematically consistent and should follow the professional split between Overall Formula, Levain Build, and Final Dough. The formula table should be the hero, not a small decorative card.

## Product summary

OpenCrumb turns messy bread recipes into organized, scalable baker’s-percentage formulas.

The target user is a serious home baker or small-batch baker who repeats doughs, scales recipes, uses preferments/levains/soakers, and wants numbers they can trust for the next bake.

The R1.0 loop is deliberately narrow:

```text
Import → Formula → Scale
```

The emotional aha moment is:

> My real recipe just became an organized, believable formula I might trust for my next bake.

## How to use with Rork Max

Start with [`RORK_PROMPT.md`](RORK_PROMPT.md). Paste it into Rork Max as the product brief.

If Rork asks for repo access, this repo is safe to use because it contains only outline material and mock data.

## Files

- [`PRODUCT_BRIEF.md`](PRODUCT_BRIEF.md) — product truth and launch scope
- [`RORK_PROMPT.md`](RORK_PROMPT.md) — pasteable prompt for Rork Max
- [`GUARDRAILS.md`](GUARDRAILS.md) — what Rork should and should not touch
- [`MOCK_DATA.md`](MOCK_DATA.md) — sample formula/import data for prototype screens
- [`BBGA_FORMULA_FORMAT.md`](BBGA_FORMULA_FORMAT.md) — BBGA-style/professional formula layout rules
- [`HAMELMAN_FORMULA_HERO.md`](HAMELMAN_FORMULA_HERO.md) — formula-first hero layout guidance
- [`SCREEN_FLOW.md`](SCREEN_FLOW.md) — target first-run and aha flow
- [`RORK_WORKFLOW.md`](RORK_WORKFLOW.md) — recommended Hermes/Rork iteration workflow and prompt pattern

## Source of truth warning

The real source of truth remains the private OpenCrumb app repo, its tests, Beads tracker, and shipping docs. Treat this repo as disposable prototype context only.
