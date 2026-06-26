# Wireframe Mode

Use this guide after the user has confirmed a PRD Lite and the current prototype step. Wireframe mode creates a low-fidelity, interactive HTML prototype for structure validation. It must not drift into high-fidelity visual design.

## Purpose

Wireframes are for validating:

- Information architecture.
- Main task path.
- Module relationships.
- Interaction logic.
- Documentation and annotation mapping.

They are not for final visual polish, brand styling, detailed illustration, production UI components, or decorative effects.

## Inputs Required

Before generating a wireframe, confirm:

- A PRD Lite exists or has been summarized in the conversation.
- The user has confirmed the current step in the PRD step plan.
- The target side/platform is known: B-side, C-side, desktop, mobile, H5, app, mini program, local module, or other.
- Design principles and risk boundaries have been confirmed.

If any of these are missing, return to `requirement-intake.md` instead of generating HTML.

## Scope Rule

Only implement the current step from the PRD step plan.

- Do not generate every page or every future step.
- Do not include Step B/C/D content unless the user explicitly makes it part of the current step.
- End with a step-level acceptance prompt: what was built, how to preview/test, known issues, and whether to adjust or continue.

## Style Modes

Choose the smallest useful wireframe style:

- `structure-wireframe`: default for B-side, data-heavy, admin, dashboard, workflow, form, and table-heavy prototypes.
- `sketch-wireframe`: useful for early C-side, mobile, consumer, gamified, exploratory, or emotional-flow prototypes.

Both styles must stay low-fidelity:

- Use grayscale and restrained accent colors only for state clarity.
- Use simple boxes, lines, labels, chips, placeholders, and basic icons made with text or CSS.
- Avoid gradients, shadows that imply polish, brand colors, real product imagery, detailed illustrations, and high-fidelity icon systems.
- Use realistic business copy instead of lorem ipsum.

## Adaptive Structure And Reference Routing

Do not make every wireframe look like the demos or the starter template.

Before creating the HTML, derive the structure from the confirmed PRD Lite:

- Product type: B-side, C-side, platform, domain, usage frequency, and task complexity.
- Current step: what the user needs to accomplish in this step only.
- Information shape: form, table, feed, timeline, kanban, wizard, map, chat, media gallery, detail view, dashboard, approval flow, or another structure.
- Primary interaction: create, browse, compare, edit, approve, search, reserve, pay, message, upload, monitor, recover, or another action.
- Design principles and risk boundaries confirmed during requirement intake.

Use `SKILL.md` Design Reference Loading Rule and `built-in-skills/design-system-reference.md` when reference selection matters. Load only the relevant reference direction for the scenario; do not load every design reference.

Examples:

- A WeChat mini program can use a compact mobile flow with list, publish action, trust cues, and reservation states.
- A SaaS approval workflow can use a desktop list/detail layout with filters, status chips, and decision actions.
- A map or location-heavy product can use map/list/detail split structure.
- A chat or AI assistant flow can use conversation, suggested actions, and result cards.
- A marketplace or community product can use feed/list, item detail, identity/trust cues, and transaction or reservation status.

The starter template is only a mechanical scaffold. Reuse its annotation and documentation pattern, not its exact layout.

## B-Side Guidance

For B-side wireframes:

- Prefer desktop-first layouts with sidebar/topbar, summary cards, filters, table/list, and detail panel.
- Preserve scanability, density, hierarchy, and operational clarity.
- Use tables only when the content is genuinely row/column data.
- Include common states only when relevant to the current step: selected row, active tab, expanded detail, empty/loading/error placeholders.

## C-Side Guidance

For C-side wireframes:

- Prefer mobile-first flows, stacked cards, clear primary action, bottom action area, and step/progress cues.
- Focus on one user path at a time.
- Confirm emotional tone and risk boundaries before representing rewards, penalties, health, money, social pressure, children, education, or AI advice.
- Avoid pretending a low-fidelity wireframe has final visual identity.

## Mobile Presentation Modes

For mobile app, H5, mini program, and other small-screen prototypes, presentation mode and requirement coverage are separate decisions.

Do not drop confirmed requirements just because the user asks for a single-screen prototype.

Choose or confirm one of these modes:

- `flow-overview`: several phone screens shown side by side to explain the main path and page relationships.
- `single-interactive-container`: one phone shell or main page with local state changes, tabs, segmented controls, drawer/bottom-sheet/modal panels, or local page switching.

Default guidance:

- Use `flow-overview` when the user wants to review the whole path, compare states, or discuss page relationships.
- Use `single-interactive-container` when the user wants an experience closer to clicking through a real app, or explicitly asks for one screen.
- If the user explicitly asks for one screen, keep the current PRD step coverage by using tabs, local page switching, expandable panels, bottom sheets, drawers, or state toggles.
- If the current step contains too many tasks to fit even with local interactions, propose splitting it into Step A1 / Step A2 before generating. List which confirmed requirements would move to each sub-step and wait for user confirmation.

Coverage check before delivery:

- Every core task in the current PRD step is visible in the UI, reachable through an interaction, or explicitly documented as deferred with user approval.
- Key data, fields, states, and risk boundaries from the confirmed PRD are preserved.
- If a confirmed requirement is represented only in the side documentation, explain why it is not shown in the current screen.
- Do not silently move confirmed requirements to a later step.

## Long Iteration Guard

Wireframes often improve through many small user tweaks. Long edit threads can cause the Agent to over-focus on the latest local change and forget the confirmed PRD or Skill baseline.

Use this guard during refinement:

- If there have been several consecutive prototype edits, briefly restate the current PRD step, presentation mode, and acceptance target before another substantial edit.
- Read the current HTML file before editing when the file is large, the context is long, or the user is asking for a correction to prior output.
- Preserve confirmed requirements, fields, states, design principles, risk boundaries, right-side documentation, and numbered pins during every edit.
- If the user's new request conflicts with the confirmed PRD or would move scope between steps, ask whether to update the PRD/step plan.
- After each edit, re-check the baseline: no external dependencies, current step only, annotations still map to documentation, core interactions still work, and local preview instructions are clear.

## Required Output

Every wireframe HTML must include:

- Previewable HTML with no external network dependencies.
- Left/main prototype area.
- Right side documentation panel.
- Numbered pin annotations on key UI elements.
- Matching numbered documentation items.
- Annotation show/hide control.
- Two-way hover/focus highlight between pins/prototype elements and documentation items.
- At least one meaningful interaction for the current step, such as tabs, filters, expand/collapse, detail panel, or state toggle.
- A short in-page note that this is a wireframe and examples are not fixed product templates.

## Documentation Panel

Use a concise but complete side document:

- 原型说明
- 功能说明
- 字段说明
- 交互说明
- 验收点

Keep documentation useful for product/front-end communication, but shorter than a PRD.

## Annotation Rules

- Use numbered circular pins only.
- Do not use SVG long connector lines.
- Use 4-6 pins for demos and normal pages unless the user requests more.
- Pins must not obscure critical labels or actions.
- Pin hover/focus highlights the relevant UI area and matching doc item.
- Doc item hover/focus highlights the matching pin and UI area.

## Template And Examples

`starter-components/wireframe-template.html` is a reusable skeleton. It demonstrates layout and interaction mechanics only.

Files under `examples/01-wireframe-demo/` are reference examples, not business templates:

- Do not copy example business content into unrelated user prototypes.
- Do not force user requests into the example layout.
- Reuse only the interaction pattern, annotation pattern, side-document pattern, and low-fidelity constraints.

## Local Preview

For standalone HTML files, open the file directly or serve the project folder locally. Before delivery, verify:

- Page loads.
- No console errors.
- No external CDN or remote assets.
- Annotations can be hidden and shown.
- Two-way hover/focus works.
- Core interactions work.
- Desktop and mobile viewports remain readable.
