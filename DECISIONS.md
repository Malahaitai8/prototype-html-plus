# Decisions

## 2026-06-26 - Step 0 Bootstrap Decisions

- Project name: `prototype-html-plus`.
- License: MIT.
- GitHub remote: `https://github.com/Malahaitai8/prototype-html-plus.git`.
- Bootstrap scope: create the full V1 skeleton, but do not implement functional Skill behavior before each step is separately confirmed.
- V1 plan persistence: commit `docs/v1-implementation-plan.md` so the project can be resumed from another machine.
- Commit development records: keep `PROGRESS.md` and `skills/prototype-html-plus/test-prompts/` in Git because they are part of the agreed development workflow.
- Do not expose development workflow as Skill capability: GitHub progress tracking and test-thread prompts must not be described as end-user Skill features.
- Ignore local-only material: scratch notes, local plan files, screenshots, renders, logs, previews, coverage, and tool caches are excluded by `.gitignore`.
- Reference code policy: do not copy reference repository code directly; use them only for research and design decisions, with license awareness.

## 2026-06-26 - Step 1 Reference Research Decisions

- Use a layered Skill structure: `SKILL.md` routes, `system-prompt.md` holds cross-mode principles, and `built-in-skills/` contains capability-specific workflows.
- Keep `SKILL.md` concise; move detailed rules into progressive-disclosure files.
- Default annotation model: numbered pins with two-way hover highlighting. SVG long connectors are removed from V1.
- Wireframe mode will support two branches later: hand-drawn wireframe and structured black/gray wireframe.
- Wireframe and high-fidelity modes must support both B-side and C-side prototypes.
- High-fidelity B-side mode will use an Ant Design-like baseline by default, without importing Ant Design as a dependency in V1.
- Data-dense dashboards and monitoring pages may borrow Carbon-style density and hierarchy principles.
- Enterprise SaaS / Microsoft-style collaboration tools may borrow Fluent UI-style restraint and consistency.
- B-side reference routing: CRM / ERP / OA / approval workflows use Ant Design; BI / monitoring / operations analytics use Carbon plus Ant Design; finance / risk / trading operations use Carbon first; internal collaboration uses Fluent UI; industrial / operations / IoT consoles use Carbon first.
- C-side reference routing: iOS app uses Apple HIG; Android / Material-style app uses Material Design 3; Chinese mobile web / H5 uses Ant Design Mobile; WeChat ecosystem uses WeUI; Tencent-style / Vue mobile web may use TDesign Mobile.
- Design references must be loaded by scene. Do not load all B-side and C-side references into context by default.
- Frontend quality gets its own built-in skill later; it must cover anti-template patterns, typography, spacing, states, responsive behavior, semantic HTML, accessibility, and realistic copy.
- Region screenshot rebuild must be audit-first: analyze the provided region, ask what to preserve or change, avoid inventing unreadable text, and generate only the requested region by default.
- Reference repositories and design systems are conceptual references only. Do not copy their code, CSS, sample HTML, or prose into this project.
- `wsdlp46/prototype-html-pin` was not directly accessible during Step 1; keep its pin-annotation direction as a project-spec requirement and verify the repository later if access becomes available.

## 2026-06-26 - Step 1 Supplemental Consumer References

- Step 1 needed a C-side supplement because the initial references leaned toward B-side admin, enterprise SaaS, data systems, and prototype mechanics.
- Added C-side reference set: Apple Human Interface Guidelines, Material Design 3, Ant Design Mobile, WeUI, and TDesign Mobile.
- Added `built-in-skills/design-system-reference.md` as a routing guide, not a full implementation step.
- Confirmed that the Skill should choose references by scenario instead of loading all design-system guidance at once.
- Confirmed that numbered pin annotation is the only V1 annotation model; long connector lines are out of scope.

## 2026-06-26 - Step 2 Requirement Intake Decisions

- Requirement intake is a PRD Lite workflow, not a decorative questionnaire.
- The Skill must first fill known information from the user's request, then ask only for blocking gaps.
- Default intake format is Markdown PRD Lite in chat; it must not assume a real interactive form.
- Each important PRD item must be marked as `已确认`, `待确认`, or `Agent 假设`.
- Ask at most 5 blocking questions per round.
- Missing core information requires clarification before prototype generation: side/platform, prototype goal, user role, output mode, scope, core modules, and key data/fields/states.
- "帮我推荐" is allowed, but recommendations must be marked as `Agent 假设` and confirmed before generation.
- "跳过，直接生成初版" produces a PRD draft with assumptions first; it does not jump directly to HTML.
- Before generating any prototype, the Agent must ask the user to confirm or revise the PRD Lite.
- In a project workspace, the Agent may suggest saving a confirmed PRD Lite as `requirements.md`, but must ask before writing it.
- Large requests must be split into a prototype queue: main path first, then expanded interactions, states, and visual polish.
- After the user answers clarification questions, the Agent must re-output the complete updated PRD Lite and run a confirmation gate before saving files or generating HTML.
- "按推荐继续" confirms assumptions only; it is not permission to generate HTML or write `requirements.md` unless the user explicitly says so.
- The prototype step plan is binding: each generation should execute only the current step by default, then ask for user acceptance before continuing.
- For every product type, design principles and risk boundaries must be confirmed before prototype generation; sensitive or emotion-heavy domains require extra care but are not the only cases.

## 2026-06-26 - Step 3 Wireframe Decisions

- Wireframe mode is a general-purpose capability, not a pair of hardcoded product templates.
- Wireframes validate information structure, main path, module relationships, fields, states, and interaction logic; they do not validate final visual style.
- Wireframe generation requires a confirmed PRD Lite, confirmed current step, known side/platform, and confirmed design principles/risk boundaries.
- The PRD step plan remains binding in wireframe mode: generate only the current step, then wait for user acceptance before continuing.
- V1 wireframe output must include a previewable single-file HTML, right-side documentation, numbered circular pins, annotation show/hide, two-way hover/focus highlight, and at least one meaningful interaction.
- Numbered circular pins remain the only annotation model in V1; SVG long connector lines are not used.
- `starter-components/wireframe-template.html` is a reusable interaction/layout skeleton, not a product design.
- `examples/01-wireframe-demo/` demonstrates B-side and C-side structure differences, but examples are not capability boundaries and must not be copied as fixed business templates.
- Wireframe structure must be derived from the confirmed PRD, platform, domain, information shape, and primary user action; low fidelity does not mean all products share one layout.
- Wireframe mode should use the existing design reference routing when platform conventions matter, loading only relevant guidance instead of every reference.
- Mobile wireframes support both multi-screen flow overview and single interactive container modes.
- User-requested single-screen mobile wireframes must preserve confirmed current-step requirements through local interactions or an explicit user-approved step split; requirements must not disappear because of screen constraints.
- Long prototype refinement needs an iteration guard: the Agent should periodically restate current PRD step/presentation mode/acceptance target, read current files when context is noisy, and re-check Skill baselines before delivery.
- B-side wireframes should usually favor desktop operational structure, density, filters, tables/lists, and detail panels when the PRD calls for them.
- C-side wireframes should usually favor mobile flow structure, primary actions, state feedback, and step cues when the PRD calls for them.

## 2026-06-26 - Step 4 High-Fidelity Decisions

- Step 4 implements Basic High-Fidelity Mode, not screenshot rebuild. Region screenshot rebuild and full screenshot reproduction remain Step 6 scope.
- High-fidelity generation supports two input paths: confirmed PRD directly to high-fidelity, and confirmed wireframe upgraded to high-fidelity.
- Before generating high-fidelity output, the Skill must declare product type, platform, current PRD step, selected official reference, why it applies, and which references are intentionally not used.
- High-fidelity mode uses `frontend-skill` for visual hierarchy, product-surface restraint, information density, realistic copy, and state completeness.
- `design-system-reference.md` remains the routing table for official references; `frontend-quality.md` is the delivery quality gate.
- Official high-fidelity references are Ant Design, Carbon Design System, Fluent 2, Apple Human Interface Guidelines, Material Design 3 / Material Web, Ant Design Mobile, WeUI, and TDesign Mobile Vue.
- Step 4 B-side demo uses Ant Design as the primary reference for admin layout, navigation, filters, tables, forms, drawers, modals, and feedback; Carbon is the secondary reference for metric density, operational hierarchy, monitoring status, and complex data readability.
- Step 4 C-side demo uses WeUI as the primary reference for WeChat mini-program rhythm, cell lists, bottom primary actions, lightweight trust prompts, sheets, and toast feedback.
- Step 4 demos must not import official UI libraries, copy their source code, or blend multiple official systems for decorative effect.
- Both high-fidelity demos must be single-file HTML with no CDN or remote resources, right-side documentation, numbered circular pins, annotation visibility toggle, two-way hover/focus highlighting, and at least two meaningful interactions.
- After user feedback, high-fidelity mode now always requires UI style confirmation before HTML generation. The basic demos remain selectable "简约基础款 / 规范交付版" references instead of a direct-generation shortcut.
- Step 4 adds two styled demo directions first: a B-side dark command center and a C-side warm lifestyle exchange. They prove that selected UI style must change layout, spacing, material, color, rhythm, and state expression, not only the primary color.

## 2026-06-26 - Step 4 Style System And Brand Asset Decisions

- Collaboration rule is now explicit: before every new functional step, new sub-capability, or scope redefinition, ask at least two rounds of questions, with at least two meaningful questions per round.
- Step 4 high-fidelity is split into two sub-capabilities that merge at generation time: style system and brand assets.
- Style system covers UI style, layout, typography, color, component density, state expression, and motion rhythm.
- Brand assets cover logo, brand character / mascot, imagery, pictograms, and icon strategy.
- Brand assets are optional. Requirement intake and UI style confirmation ask whether they are needed; if the user says no, the Skill skips that route.
- `visual-reference-library.md` records official design systems, high-adoption modern UI references, icon references, and brand asset rules.
- High-fidelity output should not use emoji as product icons by default. Use a confirmed icon strategy, usually inline SVG/CSS icons for single-file demos.
- Brand assets must be original or user-provided. Do not copy existing brand IP such as famous mascots, logos, or campaign characters.
- Network imagery is allowed when the user confirms it, but source URLs must be recorded.
- The enhanced B-side styled demo is `b-side-modern-saas-ops.html`: Linear/Vercel-like SaaS surface, restrained logo mark, and consistent line icons.
- The canonical enhanced C-side styled demo is now `c-side-ios-weekend-discovery.html`: an original iOS city-weekend discovery App with editorial imagery and a three-screen discovery, detail, and reservation path. The former fresh-grocery file was removed to avoid retaining a stale reference.

## 2026-06-28 - Step 4 App High-Fidelity Decisions

- Generic C-side mobile output must confirm iOS, Android, H5, or mini program before choosing a reference route; mini-program patterns are not the default for Apps.
- iOS high-fidelity uses Mobbin public samples for real-product visual calibration, Page Flows for task-path validation, and Apple HIG as the final platform authority.
- Android keeps the equivalent Mobbin + Page Flows + Material 3 route, but this iteration does not add an Android demo.
- Mobbin and Page Flows are research sources, not code or asset libraries. The Skill extracts layout and flow rules and must not copy brands, screenshots, copywriting, photography, illustrations, or distinctive trade dress.
- App generation requires a confirmed App Visual Reference Sheet after UI style confirmation. Public-source fallback is allowed when paid content is inaccessible and must be disclosed.
- `hi-fi-mobile-shell.html` is now a composable iOS template kit covering a native shell, discovery feed, detail page, bottom sheet, and confirmation state.
- App typography uses explicit mobile text roles, an 8-point spacing rhythm, safe areas, 44px touch targets, line clamping, and reserved space for fixed actions.
- Styled App demos hide annotation pins by default so documentation does not degrade the product's first visual impression.
