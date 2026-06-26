# V1 Implementation Plan

## Summary

`prototype-html-plus` is a Codex Skill for creating interactive HTML product prototypes with a side documentation panel. V1 should become useful before it becomes elaborate: each feature is added only after its requirements are confirmed, implemented, tested, documented, committed, and pushed.

The Skill's user-facing capability is prototype generation. GitHub progress records and test-thread prompts are development workflow requirements for this repository, not capabilities to advertise inside the Skill.

## V1 Scope

V1 must support:

- Skill foundation and Codex-specific guidance.
- Structured requirement intake for vague product ideas.
- From-scratch prototype generation.
- Wireframe mode.
- Basic high-fidelity admin mode.
- Region screenshot rebuild mode.
- HTML prototype plus side documentation.
- Numbered pin annotations.
- Local preview and verification workflow.
- Example demos and independent test prompts.

V1 does not need to support:

- Full multi-page product screenshot rebuild.
- Pixel-perfect screenshot reproduction.
- Complex design-system dependency imports.
- Figma parsing.
- PPT/PDF export.
- Full CLI packaging.
- Automated multi-agent review.

## Step-by-Step Plan

### Step 0 - Project Bootstrap

Outputs:

- Root docs: `README.md`, `ROADMAP.md`, `PROGRESS.md`, `DECISIONS.md`, `LICENSE`.
- Git hygiene: `.gitignore`.
- Skill skeleton under `skills/prototype-html-plus/`.
- Test prompt: `skills/prototype-html-plus/test-prompts/00-project-bootstrap-test.md`.
- Persistent plan: `docs/v1-implementation-plan.md`.

Acceptance:

- Directory structure exists.
- Git is initialized and remote is configured.
- `PROGRESS.md` is updated before commit and push.
- The V1 plan is sufficient for another Codex session to continue.

### Step 1 - Reference Skill Research

Outputs:

- `docs/reference-skill-analysis.md`.
- Updates to `DECISIONS.md`.
- Test prompt: `skills/prototype-html-plus/test-prompts/01-reference-analysis-test.md`.

Acceptance:

- The required reference repositories are reviewed at the instruction and architecture level.
- Borrowed ideas are recorded as concepts, not copied code.
- License and originality constraints are explicitly noted.

### Step 2 - Requirement Intake

Outputs:

- `skills/prototype-html-plus/built-in-skills/requirement-intake.md`.
- Test prompt: `skills/prototype-html-plus/test-prompts/02-requirement-intake-test.md`.

Acceptance:

- For vague input such as "我想做一个数据更新看板。", the Skill asks structured questions instead of generating a page immediately.
- The intake supports recommendations, skip-to-draft, and a requirement summary.

### Step 3 - Wireframe Mode

Outputs:

- `skills/prototype-html-plus/built-in-skills/wireframe.md`.
- `skills/prototype-html-plus/starter-components/wireframe-template.html`.
- `skills/prototype-html-plus/examples/01-wireframe-demo/`.
- Test prompt: `skills/prototype-html-plus/test-prompts/03-wireframe-test.md`.

Acceptance:

- The demo creates a previewable low-fidelity HTML prototype with a side documentation panel.
- Structure, interaction path, and page relationships are clearer than visual decoration.

### Step 4 - Basic High-Fidelity Mode

Outputs:

- `skills/prototype-html-plus/built-in-skills/hi-fi.md`.
- Starter components for admin layout, table page, and modal.
- `skills/prototype-html-plus/examples/02-hi-fi-admin-demo/`.
- Test prompt: `skills/prototype-html-plus/test-prompts/04-hi-fi-test.md`.

Acceptance:

- The demo creates a previewable admin-style HTML page with realistic B-side density and controls.
- The page includes side documentation and common interaction states.

### Step 5 - Side Documentation and Pin Annotations

Outputs:

- `skills/prototype-html-plus/built-in-skills/annotation-doc.md`.
- `skills/prototype-html-plus/starter-components/doc-panel.html`.
- `skills/prototype-html-plus/starter-components/pin-annotation.js`.
- `skills/prototype-html-plus/examples/04-annotation-doc-demo/`.
- Test prompt: `skills/prototype-html-plus/test-prompts/05-annotation-doc-test.md`.

Acceptance:

- The demo has at least four numbered pins.
- Hovering prototype elements highlights matching documentation items.
- Hovering documentation items highlights matching prototype elements.
- Annotation visibility can be toggled.

### Step 6 - Region Screenshot Rebuild

Outputs:

- `skills/prototype-html-plus/built-in-skills/region-rebuild.md`.
- `skills/prototype-html-plus/examples/03-region-rebuild-demo/`.
- Test prompt: `skills/prototype-html-plus/test-prompts/06-region-rebuild-test.md`.

Acceptance:

- The Skill asks what to preserve and what to change before generating a region prototype.
- The Skill avoids inventing unreadable screenshot text.
- The output focuses on the requested region instead of creating a full page by default.

### Step 7 - Local Preview and Verification

Outputs:

- `skills/prototype-html-plus/references/codex.md`.
- `skills/prototype-html-plus/agents/verify-html.mjs`.
- `skills/prototype-html-plus/agents/screenshot-check.mjs`.
- Test prompt: `skills/prototype-html-plus/test-prompts/07-preview-verify-test.md`.

Acceptance:

- Generated HTML can be served locally.
- Codex can open localhost, check rendering, inspect console errors, test key interactions, and fix issues before delivery.
- Every HTML demo has a local preview path.

### Step 8 - V1 Cleanup and GitHub Upload

Outputs:

- Finalized README and ROADMAP.
- Complete PROGRESS and DECISIONS records.
- All V1 test prompts.
- GitHub push and optional `v0.1.0` tag if appropriate.

Acceptance:

- V1 can be placed into a Codex project and used.
- Core demos preview locally.
- Each implemented feature has a test prompt and progress entry.

## Collaboration Rules

- Before starting each functional step, confirm the step's concrete requirements with the user.
- Do not decide key product rules without confirmation.
- Do not implement multiple V1 steps in one pass unless explicitly asked.
- Update `PROGRESS.md` before every commit and push.
- Provide a copyable new-thread test prompt after every feature.
- For every HTML demo, verify that it can be previewed locally.
- Do not copy reference repository code directly.

## Git Tracking Policy

Commit:

- Root project docs.
- Skill source files and references.
- Starter components and examples.
- Test prompts required by the development workflow.
- Progress and decision records.

Do not commit:

- `*.local.md`, `local-notes/`, `scratch/`.
- `.codex/`, `.agents/`.
- `screenshots/`, `renders/`, logs, coverage, preview output, and test result folders.
- Editor and operating-system noise.

