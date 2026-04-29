# Rork Max Workflow for OpenCrumb

## Current recommendation

Use Rork Max as a **design/prototype collaborator**, not as the production implementation authority.

The best workflow is:

```text
Hermes maintains the source-of-truth brief → Rork generates/iterates the prototype → Hermes reviews screenshots/code against OpenCrumb trust rules → brief gets tightened → repeat
```

Do not rely on chat-only correction. When Rork makes a repeatable mistake, encode the correction in this repo so the next run starts with better constraints.

## What research showed

Rork's own documentation emphasizes that better output comes from prompts that specify:

- the experience and feel, not just features
- when polish matters
- transitions/motion
- target user and mood
- the primary UX goal
- strong constraints and controlled scope

Rork Max is the Swift path. Rork's docs describe GitHub sync as the bridge from prompt-based building into professional development tools. Paid users can export generated code through GitHub, and the integration is described as two-way sync.

There does not appear to be a public automation API or MCP integration documented for driving Rork directly from Hermes. Treat direct browser automation as possible but brittle; treat GitHub sync as the reliable integration seam.

## Roles

### Hermes owns

- product truth
- prompt files
- guardrails
- mock data
- trust rubric
- screenshot/code review
- GitHub-side commits and comparisons
- deciding whether a Rork iteration is useful or a regression

### Rork owns

- fast SwiftUI prototype generation
- first-pass screen composition
- visual hierarchy experiments
- interaction/motion ideas
- disposable UI directions

### Production OpenCrumb owns

- real import logic
- tested formula math
- SwiftData models
- StoreKit/paywall implementation
- production navigation and app architecture
- Beads/TDD/review workflow

## Recommended loop

### 1. Prepare a narrow iteration prompt

Each Rork run should have one dominant objective.

Good:

> Redesign the first-session formula preview so it reads as a trust-building glimpse: written recipe excerpt → extracted structure → professional formula rows.

Bad:

> Make OpenCrumb better and more polished.

### 2. Include the non-negotiables

Every Rork prompt should repeat the constraints most likely to drift:

- iPhone-only SwiftUI
- serious home bakers
- Import → Formula → Scale
- no AI chat identity
- no recipe-manager repositioning
- formula preview earns trust before paywall
- source quantities remain visible
- unclear values are flagged, not guessed
- no impossible 0g components
- no fake baker's percentages
- no account / no tracking / local-first trust copy

### 3. Ask for screens as hypotheses

Use language like:

> Treat this as a prototype hypothesis. Prioritize clarity and trust over completeness. Do not invent new product scope.

This stops Rork from treating visual flourish as product truth.

### 4. Capture output

For each Rork result, capture at least:

- screenshot of the changed screen
- generated code diff if GitHub sync is connected
- the exact prompt used
- one-line verdict: keep / revise / reject

### 5. Hermes review pass

Hermes should evaluate each output against this checklist:

- Does the first glance communicate written recipe → formula?
- Is trust messaging visible, not hidden?
- Are source quantities present?
- Are uncertainty and review-before-save explicit?
- Is the formula mathematically plausible?
- Does it avoid generic AI/app-builder aesthetics?
- Is it screenshot-worthy without becoming decorative nonsense?
- Does it stay inside OpenCrumb R1.0?

### 6. Encode the learning

If Rork gets something wrong twice, update one of:

- `RORK_PROMPT.md`
- `SCREEN_FLOW.md`
- `GUARDRAILS.md`
- `MOCK_DATA.md`
- formula-format docs

Do not keep retyping corrections manually.

## Automation options

### Option A — Manual Rork, automated Hermes review

This is the recommended starting point.

Flow:

```text
Paste prompt into Rork → run → screenshot/export/GitHub sync → ask Hermes to review → Hermes updates brief
```

Pros:

- reliable
- no login automation fragility
- preserves human taste judgement
- fastest to start

Cons:

- still requires manual paste/run in Rork

### Option B — GitHub-sync bridge

If the Rork project is connected to GitHub, Hermes can watch and review Rork output.

Flow:

```text
Rork commits to GitHub → Hermes pulls → reviews diff/screens → writes critique/prompt patch → pushes improved brief
```

Possible Hermes automation:

- cron job checking the Rork repo for new commits
- webhook from GitHub to Hermes
- automatic diff review using the OpenCrumb trust rubric
- generated review notes in `reviews/rork/YYYY-MM-DD-iteration.md`

This is the best real integration seam because it uses documented Rork functionality.

### Option C — Browser automation

Hermes can potentially drive the Rork website through browser tools or Playwright if Paul is logged in locally.

Flow:

```text
Hermes opens Rork → pastes prompt → uploads context files → submits → waits → screenshots result
```

Risks:

- login / 2FA / session expiry
- dynamic web app selectors change
- file uploads and long-running generation may be flaky
- bot detection or browser isolation can break it
- generated output may still require human taste review

Use this only after the GitHub-review loop is working.

### Option D — Official API / MCP

No public Rork API or MCP integration was found in the docs inspected. If Rork later exposes an API, Hermes could connect via native MCP or a custom tool.

Until then, assume no stable direct API.

## Better prompting pattern

Use this structure for Rork prompts:

```text
Objective:
What one screen/flow should improve?

Product truth:
Who OpenCrumb is for, what the app does, what it is not.

Target feeling:
Calm, precise, trustworthy, native iPhone, serious baker tool.

Non-negotiable content:
Specific copy, formula rows, trust lines, constraints.

Visual direction:
Layout metaphor, hierarchy, motion, what should be hero.

Avoid:
Known failure modes.

Acceptance checklist:
What must be true when reviewing the result.
```

## Prompt template for the current issue

```text
Objective:
Redesign the first-session formula preview / aha screen for OpenCrumb.

OpenCrumb is an iPhone-only SwiftUI app for serious home bakers. It turns messy bread recipes into organized, scalable baker's-percentage formulas. The core loop is Import → Formula → Scale.

This screen is not a generic onboarding card and not a finished formula dumped onto the screen. It must be a glimpse of the transformation:

written recipe excerpt → extracted structure/checks → professional baker's formula rows

Target feeling:
Calm, precise, native iPhone, trustworthy, made for serious bakers. Useful rather than decorative.

Visual direction:
Create one compact infographic-like surface. At the top or left, show a clipped bread recipe excerpt with source quantities. In the middle, show subtle extraction/check states. At the bottom or right, show clean formula rows with weights and baker's percentages. The formula rows should still feel like the payoff.

Trust copy must be visible inside the preview:
- Source quantities stay visible
- Review every number before saving
- Unclear amounts are flagged, not guessed
- No account. No tracking. Your formulas stay on this iPhone.

Formula rules:
- Overall Formula uses total-flour baker's percentages
- Levain Build uses build percentages and may show Levain total 200%
- Final Dough uses weights only
- do not show 0g components
- do not mix Flour and Bread flour labels
- do not invent fake precision

Avoid:
- AI magic language
- chat UI
- neon sparkle visuals
- generic feature bullets
- testimonials
- recipe-manager positioning
- paywall before value

Acceptance checklist:
In one glance, a serious baker should think: my written recipe became a structured formula I can verify before saving.
```

## Best next step

Connect the Rork project to GitHub if it is not already connected. Then use GitHub as the Hermes/Rork handoff surface:

1. Rork generates.
2. GitHub sync exports.
3. Hermes reviews the diff/screenshots.
4. Hermes updates prompt/brief docs.
5. Rork reruns with tighter context.

That gives us a repeatable loop without trusting Rork with the production repo.
