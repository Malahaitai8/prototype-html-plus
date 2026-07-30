# prototype-html-plus

`prototype-html-plus` is a Codex Skill project for generating interactive HTML product prototypes with a side documentation panel. The project is developed step by step according to the V1 plan in `docs/v1-implementation-plan.md`.

V1 focuses on a practical, previewable workflow:

- Structured requirement intake before prototype generation.
- Wireframe and high-fidelity HTML prototype modes.
- Mandatory UI style confirmation before any high-fidelity output.
- App high-fidelity routing through real-product references, platform guidelines, and reusable mobile templates.
- Optional brand-asset routing for logo, illustration, mascot, image, and icon strategy.
- Region-based screenshot rebuild support in a later step.
- A side documentation panel for product, field, interaction, change, and acceptance notes.
- Numbered pin annotations with two-way hover highlighting.
- Local preview and verification guidance for every HTML demo.

## Current Status

V1 is in active step-by-step development. The project now includes requirement intake, generic wireframe mode, and Step 4 high-fidelity mode.

Step 4 currently contains:

- Basic B-side and C-side high-fidelity reference demos.
- Styled B-side demos for modern SaaS and dark command-center directions.
- A native iOS App high-fidelity baseline for C-side products.
- High-fidelity style confirmation, visual reference selection, frontend quality gates, and optional brand-asset confirmation.
- App-specific reference rules using Mobbin public samples, Page Flows task-flow review, Apple HIG for iOS, and Material 3 for Android.

Development records and test prompts remain repository workflow material, not user-facing Skill capabilities.

## Project Layout

```text
prototype-html-plus/
|-- docs/
|   `-- v1-implementation-plan.md
|-- skills/
|   `-- prototype-html-plus/
|       |-- SKILL.md
|       |-- system-prompt.md
|       |-- built-in-skills/
|       |   |-- requirement-intake.md
|       |   |-- wireframe.md
|       |   |-- hi-fi.md
|       |   |-- app-hifi.md
|       |   |-- frontend-quality.md
|       |   |-- design-system-reference.md
|       |   `-- visual-reference-library.md
|       |-- starter-components/
|       |   |-- wireframe-template.html
|       |   |-- hi-fi-admin-shell.html
|       |   `-- hi-fi-mobile-shell.html
|       |-- examples/
|       |   |-- 01-wireframe-demo/
|       |   `-- 02-hi-fi-demo/
|       |-- test-prompts/
|       `-- agents/
|-- DECISIONS.md
|-- PROGRESS.md
|-- ROADMAP.md
|-- README.md
`-- LICENSE
```

## High-Fidelity References

High-fidelity output must declare the chosen product type, platform, current step, UI style, visual references, icon strategy, and brand-asset strategy before generating HTML.

Reference routing:

- B-side management, forms, tables, and admin flows: Ant Design as the primary reference, with Carbon for dense operational data where appropriate.
- Data-intensive monitoring and command-center views: Carbon and modern SaaS references, depending on the confirmed style.
- Enterprise collaboration and Microsoft-style products: Fluent 2.
- iOS Apps: Mobbin public samples plus Page Flows task-flow review, with Apple HIG as the final platform authority.
- Android Apps: Mobbin public samples plus Page Flows task-flow review, with Material 3 as the final platform authority.
- WeChat mini programs and WeChat H5: WeUI.
- Mobile Web UI blocks: Ant Design Mobile or TDesign Mobile Vue only when the confirmed platform matches.

Mobbin and Page Flows are used as research libraries for layout, density, task flow, and interaction patterns. The Skill must not copy another product's brand, copywriting, proprietary images, distinctive visual assets, or trade dress.

## Demo Entry Points

Open these HTML files directly in a browser:

- `skills/prototype-html-plus/examples/01-wireframe-demo/b-side-data-dashboard.html`
- `skills/prototype-html-plus/examples/01-wireframe-demo/c-side-ai-fitness-app.html`
- `skills/prototype-html-plus/examples/02-hi-fi-demo/b-side-operations-console.html`
- `skills/prototype-html-plus/examples/02-hi-fi-demo/b-side-modern-saas-ops.html`
- `skills/prototype-html-plus/examples/02-hi-fi-demo/b-side-dark-command-center.html`
- `skills/prototype-html-plus/examples/02-hi-fi-demo/c-side-community-exchange-wechat.html`
- `skills/prototype-html-plus/examples/02-hi-fi-demo/c-side-warm-lifestyle-exchange.html`
- `skills/prototype-html-plus/examples/02-hi-fi-demo/c-side-ios-weekend-discovery.html`

Reusable starter shells live in `skills/prototype-html-plus/starter-components/`.

## Development Rule

This repository intentionally separates Skill capabilities from development process records. `PROGRESS.md` and `test-prompts/` support project development and validation; they are not user-facing Skill capabilities.

Project collaboration rule: before a new step, new subfeature, or scope redefinition, confirm requirements with at least two rounds of questions, with at least two meaningful questions in each round.

Project constraint: do not use any `superpower` skill while developing this project.
