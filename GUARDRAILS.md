# Guardrails for Rork Max

This repo is a public prototype outline. It is safe to connect to Rork Max because it contains no production source, no secrets, and no private repo history.

## Use Rork for

- SwiftUI UI exploration
- first-run flow
- formula preview layout
- recipe detected card
- paywall copy/layout
- mock App Store screenshot states
- visual polish
- copy refinement
- prototype navigation

## Do not use Rork for

- production OpenCrumb implementation
- real formula/scaling math
- SwiftData schema changes
- migrations
- StoreKit entitlement logic
- Gemini / AIProxy integration
- import parser logic
- repo-wide refactors
- Beads/Dolt workflow
- App Store Connect operations
- signing / provisioning

## Required product boundaries

R1.0 is:

```text
Import → Formula → Scale
```

Do not add:

- production scheduling
- backplanning
- timers
- team workflows
- accounts
- sync
- social sharing
- AI chat
- generic meal-planner features

## Trust rules

- Do not fabricate precision.
- Do not show `0g` for unknown component quantities.
- Prefer honest uncertainty.
- The user reviews before saving.
- Scaling math is deterministic, not AI-generated.
- Import is a convenience, not the identity of the product.

## Porting rule

Anything useful from Rork should be manually reviewed and selectively ported into the real private OpenCrumb repo. Do not wholesale merge generated code.
