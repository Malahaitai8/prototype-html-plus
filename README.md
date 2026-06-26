# prototype-html-plus

`prototype-html-plus` is a Codex Skill project for generating interactive HTML product prototypes with a side documentation panel. The project is being developed step by step according to the V1 plan in `docs/v1-implementation-plan.md`.

V1 focuses on a practical, previewable workflow:

- Structured requirement intake before prototype generation.
- Wireframe and basic high-fidelity HTML prototype modes.
- Region-based screenshot rebuild support.
- A side documentation panel for product, field, interaction, change, and acceptance notes.
- Numbered pin annotations with two-way hover highlighting.
- Local preview and verification guidance for every HTML demo.

## Current Status

Step 0 initializes the project skeleton only. Functional Skill instructions, starter components, demos, and verification scripts will be added in later V1 steps after each step's requirements are confirmed.

## Project Layout

```text
prototype-html-plus/
├── docs/
│   └── v1-implementation-plan.md
├── skills/
│   └── prototype-html-plus/
│       ├── SKILL.md
│       ├── system-prompt.md
│       ├── references/
│       ├── built-in-skills/
│       ├── starter-components/
│       ├── examples/
│       ├── test-prompts/
│       └── agents/
├── README.md
├── ROADMAP.md
├── PROGRESS.md
├── DECISIONS.md
└── LICENSE
```

## Development Rule

This repository intentionally separates Skill capabilities from development process records. `PROGRESS.md` and `test-prompts/` support project development and validation; they are not user-facing Skill capabilities.

