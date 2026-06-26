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
- Default annotation model: numbered pins with two-way hover highlighting. SVG long connectors are optional only for simple pages.
- Wireframe mode will support two branches later: hand-drawn wireframe and structured black/gray wireframe.
- High-fidelity mode will use an Ant Design-like B-side baseline by default, without importing Ant Design as a dependency in V1.
- Data-dense dashboards and monitoring pages may borrow Carbon-style density and hierarchy principles.
- Enterprise SaaS / Microsoft-style collaboration tools may borrow Fluent UI-style restraint and consistency.
- Frontend quality gets its own built-in skill later; it must cover anti-template patterns, typography, spacing, states, responsive behavior, semantic HTML, accessibility, and realistic copy.
- Region screenshot rebuild must be audit-first: analyze the provided region, ask what to preserve or change, avoid inventing unreadable text, and generate only the requested region by default.
- Reference repositories and design systems are conceptual references only. Do not copy their code, CSS, sample HTML, or prose into this project.
- `wsdlp46/prototype-html-pin` was not directly accessible during Step 1; keep its pin-annotation direction as a project-spec requirement and verify the repository later if access becomes available.

