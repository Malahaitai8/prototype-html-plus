---
name: prototype-html-plus
description: Generate interactive HTML product prototypes with a side documentation panel for product managers, requirement design, and frontend handoff. Use when Codex needs to turn a vague product idea, wireframe request, high-fidelity admin page request, or region screenshot rebuild request into previewable HTML with feature notes, field notes, interaction notes, change notes, acceptance points, and numbered annotations.
---

# prototype-html-plus

## Overview

Use this Skill to create product prototype artifacts that combine:

- A previewable interactive HTML prototype.
- A side documentation panel for product and frontend communication.
- Numbered pin annotations that connect interface elements to documentation items.
- Local preview and verification before delivery.

This Skill is under V1 construction. Follow the built-in skill files as they are added during V1. If a requested capability has not been implemented yet, explain that it belongs to a later V1 step and ask for the missing requirements instead of inventing rules.

## Requirement Intake Rule

When the user gives a vague idea or asks for a prototype without enough detail, do not immediately generate HTML. Use `built-in-skills/requirement-intake.md` to produce a PRD Lite draft, mark confirmed facts / pending questions / Agent assumptions, ask at most 5 blocking questions, then re-output the complete updated PRD Lite for confirmation. Do not save `requirements.md` or generate HTML until the user explicitly confirms that action.

The PRD step plan is binding: execute only the current step by default, complete it, show preview/test/known issues, then wait for user acceptance before moving to the next step.

## V1 Capability Routing

- For vague product ideas or under-specified prototype requests, use `built-in-skills/requirement-intake.md` before generating HTML.
- For low-fidelity structure-first prototypes, use `built-in-skills/wireframe.md` once available.
- For high-fidelity admin prototypes, use `built-in-skills/hi-fi.md` once available.
- For region screenshot rebuilds, use `built-in-skills/region-rebuild.md` once available.
- For side documentation and annotations, use `built-in-skills/annotation-doc.md` once available.
- For frontend quality checks, use `built-in-skills/frontend-quality.md` once available.
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
- C-side iOS app: Apple Human Interface Guidelines.
- C-side Android / Material-style app: Material Design 3.
- C-side Chinese mobile web / H5: Ant Design Mobile.
- WeChat ecosystem / mini program / WeChat H5: WeUI.
- Tencent-style or Vue mobile web: TDesign Mobile.

If the platform is unclear and affects the result, ask a short clarification question or use the user's "help me recommend" instruction. All annotation uses numbered pins; do not use SVG long connector lines.

## Current Rule

Do not describe repository development requirements, GitHub progress tracking, or test-thread prompts as user-facing Skill features. Those records support development of this Skill, not the Skill's runtime behavior.
