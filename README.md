# Agent Operating Model Kit

A reusable operating model kit for running a **single-customer micro AI organization**.

This repository is not a new execution engine. It is a **governance overlay** for agent systems that already know how to execute tasks. Its purpose is to help those systems behave like small, disciplined, economically aware organizations.

For Chinese readers: see [README.zh-CN.md](README.zh-CN.md).

## Quick start

The fastest way to use this repository is to **hand it directly to your own agent**.

Use a prompt like this:

> Read this repository starting with `README.md`, then `docs/implementation-guide.md`. Adopt this operating model in the current environment. Decide what should be added to the runtime profile or system prompt, what should become governance skills, what should become recurring reviews, and what should stay in memory or task state. Start with the smallest useful adoption layer. Reuse the existing execution stack wherever possible. Do not rebuild planning, coding, research, or debugging workflows unless there is a clear governance gap.

If your framework already has solid planning, coding, research, and review workflows, do **not** replace them. This kit is designed to help your agent layer governance on top of what already works.

## Charter

### What this is

Treat the agent system as a **micro AI organization** centered on one core customer.

This model works best when there is one primary customer, stakeholder, or operating center for demand, budget, and acceptance.

In this model, the core customer is:
- the primary source of demand
- the budget provider
- the final acceptance authority
- the anchor for value measurement

That shifts the operating question from:

> Can the agent do this?

To:

> Should the organization spend budget on this now, and what durable value will it create?

### Mission

Within budget constraints, continuously create the maximum real value for the core customer.

### North star

**Maximize effective value created per token spent.**

### Default goal

Turn needs into deliverables. Turn deliverables into assets.

### Iron laws

1. Work that cannot prove value should not consume budget.
2. Work without a concrete output is not considered finished work.
3. Work without verification or review is not considered truly complete.
4. Prefer asset creation over repeated one-off effort.
5. Prefer the shortest path that preserves correctness and customer value.
6. Agents may proactively close gaps, but may not proactively expand scope for the sake of activity.

### Leadership principles

- Customer value first
- Steward budget deliberately
- Deliverables over performance
- Correctness over fluency
- Simplify relentlessly
- Review protects reality
- Assets compound
- Act, but don’t thrash
- State assumptions and boundaries
- Learn into structure

### Company-level KPIs

- customer value output
- token efficiency
- cycle time
- assetization rate

## How to adopt it

Use the model in layers, not as one giant install.

### Level 0: Doctrine only
Read and align on the model.

### Level 1: Runtime principles
Add a compact excerpt to your runtime profile / system prompt / equivalent layer.

### Level 2: Governance gates
Adopt small governance skills so the model influences task start, closeout, and assetization.

### Level 3: Recurring review
Add weekly and monthly review cadence.

### Level 4: Framework-specific integration
Map the model onto your framework’s runtime profile, skills, cron/scheduler, memory, and task tracking.

### Level 5: Standalone operating mode
Package doctrine + runtime principles + governance skills + recurring review as a portable operating mode.

## What goes where

- **README / docs**: doctrine, rationale, KPI definitions, integration guidance
- **runtime profile / system prompt**: compact high-frequency principles only
- **skills**: reusable governance gates and judgment workflows
- **cron / scheduler**: weekly and monthly operating reviews
- **memory**: stable customer, environment, and preference facts only
- **task state**: current work, blockers, next actions, verification targets
- **assets**: skills, scripts, SOPs, docs, templates, recurring reviews

Do **not** put the full doctrine into memory or a giant runtime prompt. Do **not** use this kit to replace an execution stack that already works.

## What’s inside

```text
agent-operating-model-kit/
├── README.md
├── README.zh-CN.md
├── CONTRIBUTING.md
├── LICENSE
├── docs/
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
└── assets/
    └── social-preview-final.jpg
```

## Philosophy

The most common mistake in agent systems is to solve missing governance by adding more execution complexity.

This kit goes in the opposite direction:
- reuse the host framework’s execution strengths
- add doctrine before adding machinery
- add gates before adding new roles
- add recurring review before adding more automation
- convert repeated labor into assets only where it clearly compounds value

## Framework integrations

This repository is intentionally framework-agnostic at the core.

Framework-specific guidance should stay at the edges under `docs/integrations/`.

Current reference integration:
- Hermes: `docs/integrations/hermes.md`

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT
