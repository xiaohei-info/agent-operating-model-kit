# Agent Operating Model Kit

A reusable operating model kit for running a **single-customer micro AI organization**.

This repository is not a new execution engine. It is a **governance overlay** for agent systems that already know how to execute tasks. Its job is to help those systems behave like small, disciplined, economically aware organizations.

For Chinese readers: see [README.zh-CN.md](README.zh-CN.md).

## Quick start

The fastest way to use this repository is to **hand it directly to your own agent**.

Tell your agent something like:

> Read `README.md` first. Then read `docs/operating-doctrine.md`, `docs/layering.md`, `docs/adoption-playbook.md`, and `docs/what-goes-where.md`. Adopt this operating model in the current environment. Decide what should live in soul/profile, skills, cron, memory, docs, and task state. Start with the lowest maturity level that makes sense. Do not rebuild the existing execution stack unless there is a clear governance gap.

If your framework already has solid planning, coding, research, and review workflows, do **not** replace them. This kit is designed to help your agent layer governance on top of what already works.

## How it works

The kit adds a governance layer on top of an existing agent framework.

Instead of asking only:

> Can the agent do this?

It forces the system to ask:

> Should the organization spend budget on this now, and what durable value will it create?

The model is built around a few core ideas:

- one core customer anchors demand, budget, and acceptance
- the mission is to create the maximum real value within budget constraints
- the north star is **effective value created per token spent**
- needs should become deliverables, and deliverables should become assets
- work that cannot prove value should not consume budget
- work without a concrete output or fresh verification is not truly complete

In practice, the kit works by combining:
- a doctrine document
- a compact runtime principles excerpt
- governance skills that create decision and completion gates
- recurring review prompts for KPI and doctrine audits
- framework-specific integration guidance when needed

## Installation / Adoption

This repository is meant to be adopted in layers, not installed as one giant bundle.

### Level 0: Doctrine only
Read the model and align on terminology.

### Level 1: Runtime principles
Add a compact excerpt to your agent's soul/profile/system prompt.

### Level 2: Governance gates
Adopt the small governance skills so the model influences task start, task closeout, and assetization.

### Level 3: Recurring review
Add weekly and monthly review cadence using the provided cron templates.

### Level 4: Framework-specific integration
Document how the model maps onto your framework's soul, skills, cron, memory, and task tracking.

### Level 5: Standalone operating mode
Package doctrine + runtime principles + governance skills + recurring review as a portable operating mode.

For a fuller rollout path, see [docs/adoption-playbook.md](docs/adoption-playbook.md).

For the shortest placement rules, see [docs/what-goes-where.md](docs/what-goes-where.md).

For directly handing the kit to another agent, see [examples/generic/example-agent-handoff.md](examples/generic/example-agent-handoff.md).

## What's inside

```text
agent-operating-model-kit/
├── README.md
├── README.zh-CN.md
├── AGENTS.md
├── CONTRIBUTING.md
├── LICENSE
├── docs/
│   ├── operating-doctrine.md
│   ├── kpi.md
│   ├── layering.md
│   ├── adoption-playbook.md
│   ├── what-goes-where.md
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
│   ├── soul/
│   │   ├── hermes-soul-excerpt.md
│   │   └── generic-agent-soul-excerpt.md
│   ├── cron/
│   │   ├── weekly-operating-review.md
│   │   └── monthly-operating-audit.md
│   └── review/
│       └── task-closeout-template.md
└── examples/
    ├── generic/
    │   ├── example-adoption.md
    │   └── example-agent-handoff.md
    └── hermes/
        └── example-adoption.md
```

### Docs
Long-form doctrine, KPI definitions, layering, and adoption guidance.

### Skills
Small governance skills that sit **above** execution skills rather than replacing them.

### Templates
Copyable soul excerpts, cron prompts, and review templates.

### Examples
Reference rollouts. These are examples, not the only valid way to adopt the model.

## Philosophy

The most common mistake in agent systems is to solve missing governance by adding more execution complexity.

This kit goes in the opposite direction:
- reuse the host framework's execution strengths
- add doctrine before adding machinery
- add gates before adding new roles
- add recurring review before adding more automation
- convert repeated labor into assets only where it clearly compounds value

## Framework integrations

This repository is intentionally framework-agnostic at the core.

Framework-specific guidance should stay at the edges:
- integration docs under `docs/integrations/`
- reference rollouts under `examples/`

Current reference integration:
- Hermes: `docs/integrations/hermes.md`

The repo intentionally keeps framework-specific examples minimal. The generic example and generic agent handoff should be enough for many environments; framework-specific notes are there only as reference edges.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT
