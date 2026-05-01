# Agent Operating Model Kit

A reusable operating model for running an agent system as a **single-customer micro AI organization**.

This repository is not a new execution engine. It is a **governance package**: a canonical charter, reusable governance skills, optional runtime reference surfaces, and optional recurring review prompts that can be layered onto an execution stack that already works.

For Chinese readers: see [README.zh-CN.md](README.zh-CN.md).

## Why this repo exists

Most agent systems do not fail because they cannot execute. They fail because they lack:
- a stable definition of customer value
- budget discipline
- credible completion criteria
- recurring review
- structural assetization

This kit packages those governance pieces in a form humans can evaluate and agents can adopt.

## Signature operating ideas

What makes this kit distinctive is not just its file structure, but its operating ideas:

- **Token is budget** — model usage, tool calls, coordination overhead, and operator attention are treated as spend, not invisible free goods.
- **No concrete output means not finished** — visible activity and persuasive narration do not count as completion.
- **No verification means not complete** — claims must be supported by fresh evidence appropriate to the task.
- **Treat the agent system as a micro AI organization** — work is governed around one core customer, not around generic assistant behavior.
- **Turn deliverables into assets** — repeated work should become skills, docs, scripts, templates, or recurring reviews instead of staying trapped in raw conversation.
- **Govern execution; do not replace it** — the kit is meant to improve an existing host framework, not compete with it.

These ideas are the real product. The repository structure exists to make them portable.

## Quickstart

If you only have this repo link and need a correct first pass:

1. Read [`docs/operating-doctrine.md`](docs/operating-doctrine.md) to understand the methodology.
2. Read [`docs/implementation-guide.md`](docs/implementation-guide.md) to map it into the host environment.
3. Choose an adoption profile:
   - **Minimum**: doctrine + compressed runtime guidance + manual governance gates
   - **Standard**: minimum + reusable governance skills + memory boundaries
   - **Full**: standard + recurring weekly/monthly governance reviews
4. Keep the host's existing execution strengths.
5. Install only the governance surfaces the host can actually support.
6. Run the post-install smoke test from the implementation guide.

## How to read this repository

This repository contains several **different kinds of artifacts**. They cooperate, but they are not the same concept.

### 1. Core skill artifacts
These carry the actual operating model and reusable governance logic.

- [`docs/operating-doctrine.md`](docs/operating-doctrine.md) — canonical charter / doctrine
- [`skills/`](skills/) — reusable governance skills
- [`templates/review/task-closeout-template.md`](templates/review/task-closeout-template.md) — reusable closeout structure

### 2. Integration surfaces
These help another agent or framework map the package into its own runtime.

- [`AGENTS.md`](AGENTS.md) — thin operational loader / read router
- [`SOUL.md`](SOUL.md) — compressed runtime guidance for high-frequency loading
- [`MEMORY.md`](MEMORY.md) — boundaries for durable memory
- [`docs/implementation-guide.md`](docs/implementation-guide.md) — how to map the package into a host stack
- [`docs/integrations/hermes.md`](docs/integrations/hermes.md) — Hermes-specific reference integration

### 3. Operational surfaces
These are optional surfaces for recurring governance, not universal requirements for every skill repo.

- [`templates/cron/`](templates/cron/) — recurring operating review prompts

### 4. Deployment guides
These explain how the reusable pieces should be installed or adapted.

- [`skills/README.md`](skills/README.md) — skill deployment guidance
- [`templates/cron/README.md`](templates/cron/README.md) — scheduled workflow deployment guidance

## Packaging principle

The key packaging principle is simple:

> Keep the canonical doctrine explicit. Keep runtime guidance compressed. Keep deployment and operations separate from the skill artifact itself.

## Adoption profiles

### Minimum
Use when the host has limited extensibility.

Install:
- canonical doctrine
- compressed runtime guidance if possible
- manual use of the three governance gates

### Standard
Use when the host can load reusable skills or equivalent procedural assets.

Install:
- everything in minimum
- reusable governance skills
- memory boundaries if persistent memory exists

### Full
Use when the host also supports recurring scheduled review.

Install:
- everything in standard
- weekly operating review
- monthly doctrine audit

See [`docs/implementation-guide.md`](docs/implementation-guide.md) for the capability-based landing algorithm and smoke test.

## Directly usable assets

### Canonical doctrine and mapping docs
- [`docs/operating-doctrine.md`](docs/operating-doctrine.md)
- [`docs/implementation-guide.md`](docs/implementation-guide.md)
- [`MEMORY.md`](MEMORY.md)

### Runtime / host adaptation references
- [`AGENTS.md`](AGENTS.md)
- [`SOUL.md`](SOUL.md)
- [`docs/integrations/hermes.md`](docs/integrations/hermes.md)

### Governance skills
- [`skills/operating-gates/SKILL.md`](skills/operating-gates/SKILL.md)
- [`skills/delivery-review-gates/SKILL.md`](skills/delivery-review-gates/SKILL.md)
- [`skills/assetization-closeout/SKILL.md`](skills/assetization-closeout/SKILL.md)
- [`skills/README.md`](skills/README.md)

### Optional recurring governance prompts
- [`templates/cron/weekly-operating-review.md`](templates/cron/weekly-operating-review.md)
- [`templates/cron/monthly-operating-audit.md`](templates/cron/monthly-operating-audit.md)
- [`templates/cron/README.md`](templates/cron/README.md)

### Review template
- [`templates/review/task-closeout-template.md`](templates/review/task-closeout-template.md)

## What good adoption looks like

A good landing of this kit should make the host system:
- more explicit about value before scaling up work
- more evidence-based before claiming completion
- better at turning repeated work into durable assets
- more budget-aware without becoming bureaucratic
- clearer about what belongs in doctrine, runtime, memory, skills, and recurring review

If adoption mainly adds ceremony or duplicates strong local workflows, it has gone wrong.

## Repository layout

```text
agent-operating-model-kit/
├── README.md
├── README.zh-CN.md
├── AGENTS.md
├── SOUL.md
├── MEMORY.md
├── CONTRIBUTING.md
├── docs/
│   ├── operating-doctrine.md
│   ├── implementation-guide.md
│   ├── social-preview.md
│   └── integrations/
│       └── hermes.md
├── skills/
│   ├── README.md
│   ├── operating-gates/
│   │   └── SKILL.md
│   ├── delivery-review-gates/
│   │   └── SKILL.md
│   └── assetization-closeout/
│       └── SKILL.md
├── templates/
│   ├── cron/
│   │   ├── README.md
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

## For Agents

If you are an adopting agent, use this repository as a **mapping reference**, not as a blind overwrite package.

### Read order
1. [`README.md`](README.md)
2. [`docs/operating-doctrine.md`](docs/operating-doctrine.md)
3. [`docs/implementation-guide.md`](docs/implementation-guide.md)
4. Optional, when helpful:
   - [`AGENTS.md`](AGENTS.md)
   - [`SOUL.md`](SOUL.md)
   - [`MEMORY.md`](MEMORY.md)
   - [`skills/README.md`](skills/README.md)
   - [`templates/cron/README.md`](templates/cron/README.md)
   - [`docs/integrations/hermes.md`](docs/integrations/hermes.md)

### Minimal landing task
Determine which parts of this package belong in the host environment as:
- canonical doctrine
- reusable skills
- runtime guidance
- durable memory boundaries
- scheduled or recurring governance

Then choose the smallest adoption profile that preserves the methodology.

Do not assume every surface in this repository must be installed. Some are **core artifacts**, some are **integration references**, and some are **optional operational surfaces**.

If the host framework already has strong planning, coding, research, debugging, verification, or scheduling workflows, reuse them and add only the governance pieces that create real value.

## Framework integrations

Core doctrine stays framework-agnostic.

Current reference edge integration:
- Hermes: [docs/integrations/hermes.md](docs/integrations/hermes.md)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT
