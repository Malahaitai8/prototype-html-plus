---
name: prototype-html-plus
description: Generate interactive HTML product prototypes with a side documentation panel for product managers, requirement design, and frontend handoff. Use when Codex needs to turn a vague product idea, wireframe request, high-fidelity prototype request, or region screenshot rebuild request into previewable HTML with feature notes, field notes, interaction notes, change notes, acceptance points, and numbered annotations.
---

# prototype-html-plus

## Overview

Use this Skill to create product prototype artifacts that combine:

- A previewable interactive HTML prototype.
- A side documentation panel for product and frontend communication.
- Numbered pin annotations that connect interface elements to documentation items.
- Local preview and verification before delivery.

This Skill is under V1 construction. Follow the built-in skill files as they are added during V1. If a requested capability has not been implemented yet, explain that it belongs to a later V1 step and ask for the missing requirements instead of inventing rules.

## Collaboration Confirmation Rule

Before every new functional step, new sub-capability, or scope redefinition, ask the user at least two rounds of questions. 每到新步骤 / 新子功能 / 范围重定义前，至少两轮问题，每轮不少于两个有意义的问题. The first round should confirm direction and boundaries; the second round should confirm implementation details and acceptance criteria.

Do not write a final plan or implement the step before the two confirmation rounds are complete, unless the user is explicitly asking to implement an already confirmed plan.

## Requirement Intake Rule

When the user gives a vague idea or asks for a prototype without enough detail, do not immediately generate HTML. Use `built-in-skills/requirement-intake.md` to produce a PRD Lite draft, mark confirmed facts / pending questions / Agent assumptions, ask at most 5 blocking questions, then re-output the complete updated PRD Lite for confirmation. Do not save `requirements.md` or generate HTML until the user explicitly confirms that action.

The PRD step plan is binding: execute only the current step by default, complete it, show preview/test/known issues, then wait for user acceptance before moving to the next step.

## Wireframe Rule

When the user asks for a low-fidelity wireframe and the PRD Lite/current step/design boundaries have already been confirmed, use `built-in-skills/wireframe.md`.

Wireframe output must stay generic and PRD-driven:

- Execute only the current step in the confirmed PRD step plan.
- Choose structure from the specific PRD, platform, domain, information shape, and primary user action.
- Use the Design Reference Loading Rule to pick only relevant reference guidance when it affects structure or platform conventions.
- For mobile, H5, app, and mini-program wireframes, choose or confirm whether the output is a multi-screen flow overview or a single interactive container. A single-screen request must not drop confirmed PRD requirements; use local interactions or propose a step split if needed.
- Use low-fidelity structure, flow, fields, states, interactions, right-side documentation, and numbered pin annotations.
- Do not turn example files into fixed business templates.
- Do not reuse example business copy or modules unless the user's PRD asks for the same domain.
- Finish by showing local preview/test method, changed files, known issues, and a confirmation question before continuing.

## High-Fidelity Rule

When the user asks for a high-fidelity prototype and the PRD Lite/current step/design boundaries have already been confirmed, use `built-in-skills/hi-fi.md`. If the confirmed platform is iOS or Android, also use `built-in-skills/app-hifi.md`.

High-fidelity output must be reference-locked before generation:

- If the user chooses high-fidelity, first produce and confirm a UI Style Confirmation sheet. Do not generate HTML until the user confirms the UI style.
- During requirement intake or UI style confirmation, ask whether logo, brand character, imagery, or icon strategy is needed. If not needed, explicitly skip the brand-asset route.
- State the product type, platform, current PRD step, selected official reference, why it applies, and which official references are intentionally not used.
- State whether the confirmed style route is `basic-hifi` or `styled-hifi`.
- Use `built-in-skills/design-system-reference.md` as the official routing table, `built-in-skills/visual-reference-library.md` for modern UI/icon/brand references, and `built-in-skills/frontend-quality.md` as the quality gate.
- For iOS or Android App output, complete and confirm the App Visual Reference Sheet in `built-in-skills/app-hifi.md`. Use Mobbin public samples for real-product composition, Page Flows for task-flow validation, and the selected platform guideline as the final authority.
- Use `frontend-skill` principles for visual hierarchy, information density, realistic copy, state completeness, and restrained product UI.
- Do not use emoji as product icons by default. Use a confirmed icon strategy, usually inline SVG/CSS icons for single-file demos.
- Brand assets must be original or user-provided. Do not copy existing mascot, logo, or brand IP.
- Support both direct PRD-to-high-fidelity generation and low-fidelity-to-high-fidelity upgrades.
- Do not implement screenshot region rebuild or full screenshot reproduction in this mode; those belong to Step 6.
- Keep the output single-file, previewable, dependency-free, documented, annotated, and limited to the current PRD step.

## Iteration Memory Rule

During long prototype refinement, do not rely on memory alone.

- After several rounds of user tweaks, briefly restate the current PRD step, presentation mode, and acceptance target before making another large change.
- If the user request conflicts with the confirmed PRD, ask whether to update the PRD instead of silently changing scope.
- Before delivery after iterative edits, re-check the Skill baseline: current step only, confirmed requirements preserved, right-side documentation, numbered pins, local preview, no external dependencies, and user acceptance before continuing.
- If context becomes noisy or the prototype file is large, read the current source file and any saved requirement notes before editing.

## V1 Capability Routing

- For vague product ideas or under-specified prototype requests, use `built-in-skills/requirement-intake.md` before generating HTML.
- For low-fidelity structure-first prototypes with confirmed requirements, use `built-in-skills/wireframe.md`.
- For high-fidelity prototypes with confirmed requirements, use `built-in-skills/hi-fi.md`.
- For iOS or Android high-fidelity App prototypes, also use `built-in-skills/app-hifi.md`.
- For region screenshot rebuilds, use `built-in-skills/region-rebuild.md` once available.
- For side documentation and annotations, use `built-in-skills/annotation-doc.md` once available.
- For frontend quality checks, use `built-in-skills/frontend-quality.md`.
- For design-system reference selection, use `built-in-skills/design-system-reference.md`.
- For Codex preview guidance, use `references/codex.md` once available.

## Design Reference Loading Rule

Do not load every design-system reference at once. First identify whether the prototype is B-side or C-side, then load only the relevant guidance:

- B-side admin / management: Ant Design-like guidance.
- Data-dense dashboards / monitoring / analysis: Ant Design plus Carbon-like guidance.
- Enterprise SaaS / Microsoft-style collaboration: Fluent UI-like guidance.
- CRM / ERP / OA / approval workflows: Ant Design-like guidance.
- Finance / risk control / trading operations: Carbon-like density plus Ant Design-like forms and actions.
- Industrial / operations / IoT consoles: Carbon-like hierarchy plus Ant Design-like admin controls.
- C-side iOS app: Mobbin public App samples for visual calibration, Page Flows for task paths, and Apple Human Interface Guidelines as the platform authority.
- C-side Android / Material-style app: Mobbin public App samples for visual calibration, Page Flows for task paths, and Material Design 3 as the platform authority.
- C-side Chinese mobile web / H5: Ant Design Mobile.
- WeChat ecosystem / mini program / WeChat H5: WeUI.
- Tencent-style or Vue mobile web: TDesign Mobile.

If the platform is unclear and affects the result, ask a short clarification question or use the user's "help me recommend" instruction. All annotation uses numbered pins; do not use SVG long connector lines.

## Current Rule

Do not describe repository development requirements, GitHub progress tracking, or test-thread prompts as user-facing Skill features. Those records support development of this Skill, not the Skill's runtime behavior.
