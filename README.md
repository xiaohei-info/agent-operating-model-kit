# Agent Operating Model Kit

A reusable operating model for running an agent system as a **single-customer micro AI organization**.

This repository is not a new execution engine. It is a **governance package**: a portable charter, thin always-loaded guidance, governance skills, and recurring review prompts that can be layered onto an execution stack that already works.

For Chinese readers: see [README.zh-CN.md](README.zh-CN.md).

## Why this repo exists

Most agent systems do not fail because they cannot execute. They fail because they lack:
- a stable definition of customer value
- budget discipline
- credible completion criteria
- recurring review
- structural assetization

This kit packages those governance pieces in a form another agent can actually install.

## Packaging model

This repo now follows a stronger split between **full doctrine** and **always-loaded operating surfaces**:

- `docs/operating-doctrine.md` — full charter / canonical doctrine
- `AGENTS.md` — thin operational loader for another agent
- `SOUL.md` — compressed runtime charter for high-frequency loading
- `skills/` — reusable governance gates
- `templates/cron/` — recurring weekly/monthly review prompts
- `templates/review/` — closeout structure for delivery review
- `docs/implementation-guide.md` — how to land this into another stack
- `docs/integrations/hermes.md` — Hermes-specific mapping

That is the key packaging principle:

> Keep the always-loaded layer short. Keep the full doctrine canonical and separate.

## Quick start

The fastest path is to hand this repository to your agent and ask it to adopt the smallest useful layer.

Suggested prompt:

> Read `README.md`, then `AGENTS.md`, then `SOUL.md`, then `docs/implementation-guide.md`. Use `docs/operating-doctrine.md` as the full charter reference. Map this kit into the current environment without replacing a mature execution stack. Decide what belongs in the runtime layer, what should become governance skills, what should run on a recurring schedule, and what should stay out of memory. Start with the smallest useful adoption layer and report the concrete file / skill / cron changes you recommend.

If your framework already has solid planning, coding, research, debugging, and verification workflows, **do not replace them**. This kit is designed to govern them, not rebuild them.

## How another agent should land this

### Step 1 — Read in the right order

1. `README.md` — understand the package and adoption path
2. `AGENTS.md` — understand the loader / routing pattern
3. `SOUL.md` — understand the compressed runtime principles
4. `docs/operating-doctrine.md` — read when you need the full charter
5. `docs/implementation-guide.md` — map the pieces into the host stack
6. `docs/integrations/hermes.md` — if the target stack is Hermes

### Step 2 — Install only the smallest useful layer first

Use layers rather than a giant one-shot install:

- **Level 0 — doctrine**: align on the model
- **Level 1 — runtime layer**: install the compressed principles from `SOUL.md`
- **Level 2 — governance skills**: add the three governance gates from `skills/`
- **Level 3 — recurring review**: wire the weekly/monthly prompts from `templates/cron/`
- **Level 4 — framework mapping**: connect runtime / skills / cron / memory / task state to the host stack
- **Level 5 — portable mode**: keep the package reusable across projects or profiles

### Step 3 — Keep the layers clean

- put **full doctrine** in docs, not memory
- keep **runtime prompts** compressed and high-frequency only
- put **repeatable judgment** in skills
- put **recurring governance** in cron / scheduler prompts
- keep **memory** for stable facts only
- keep **task state** for active execution only

## What goes where

- **`docs/operating-doctrine.md`**: full charter, rationale, KPIs, governing logic
- **`AGENTS.md`**: the read router that tells another agent what to load first and when to escalate to deeper docs
- **`SOUL.md`**: compact operating principles for high-frequency prompt loading
- **`skills/`**: governance gates for start, closeout, and assetization
- **`templates/cron/`**: scheduled weekly and monthly governance reviews
- **`templates/review/`**: delivery closeout shape
- **memory**: stable customer / environment / preference facts only
- **task state**: current work, blockers, next actions, verification targets
- **assets**: skills, SOPs, docs, scripts, templates, recurring reviews

## Directly usable assets

### Runtime surfaces
- [`AGENTS.md`](AGENTS.md)
- [`SOUL.md`](SOUL.md)
- [`docs/operating-doctrine.md`](docs/operating-doctrine.md)

### Governance skills
- [`skills/operating-gates/SKILL.md`](skills/operating-gates/SKILL.md)
- [`skills/delivery-review-gates/SKILL.md`](skills/delivery-review-gates/SKILL.md)
- [`skills/assetization-closeout/SKILL.md`](skills/assetization-closeout/SKILL.md)

### Recurring review prompts
- [`templates/cron/weekly-operating-review.md`](templates/cron/weekly-operating-review.md)
- [`templates/cron/monthly-operating-audit.md`](templates/cron/monthly-operating-audit.md)

### Closeout template
- [`templates/review/task-closeout-template.md`](templates/review/task-closeout-template.md)

## Repository layout

```text
agent-operating-model-kit/
├── README.md
├── README.zh-CN.md
├── AGENTS.md
├── SOUL.md
├── CONTRIBUTING.md
├── docs/
│   ├── operating-doctrine.md
│   ├── implementation-guide.md
│   ├── social-preview.md
│   └── integrations/
│       └── hermes.md
├── skills/
│   ├── operating-gates/
│   │   └── SKILL.md
│   ├── delivery-review-gates/
│   │   └── SKILL.md
│   └── assetization-closeout/
│       └── SKILL.md
├── templates/
│   ├── cron/
│   │   ├── weekly-operating-review.md
│   │   └── monthly-operating-audit.md
│   └── review/
│       └── task-closeout-template.md
└── assets/
    └── social-preview-final.jpg
```

## Philosophy

This package is intentionally conservative:
- reuse the host framework's execution strengths
- add doctrine before adding machinery
- add gates before adding roles
- add recurring review before adding more automation
- keep always-loaded files short
- turn repeated work into assets only when it clearly compounds value

## Full charter

For the complete doctrine, read:
- [docs/operating-doctrine.md](docs/operating-doctrine.md)

## Framework integrations

Core doctrine stays framework-agnostic.

Current reference edge integration:
- Hermes: [docs/integrations/hermes.md](docs/integrations/hermes.md)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT
