# AGENTS.md

This file is the **thin operational loader** for the Agent Operating Model Kit.

Use it when another agent, profile, or framework needs to understand how to adopt this repository without reading everything into high-frequency context.

## Default read order

Read in this order:
1. `README.md`
2. `docs/operating-doctrine.md`
3. `docs/implementation-guide.md`

Then read on demand when mapping into a host:
- `SOUL.md` — when the host has a runtime guidance surface
- `MEMORY.md` — when the host has durable memory
- `skills/README.md` — when the host can install or emulate governance skills
- `templates/cron/README.md` — when the host can schedule or manually perform recurring governance

Read on demand:
- `docs/operating-doctrine.md` — when you need the full charter, packaging rationale, KPI frame, or doctrine audit standard
- `MEMORY.md` — when deciding what durable facts belong in memory vs other surfaces
- `skills/README.md` — when deciding how reusable governance skills should be installed or adapted
- `templates/cron/README.md` — when deciding how scheduled governance should be installed or adapted
- `docs/integrations/hermes.md` — when the target environment is Hermes
- `skills/operating-gates/SKILL.md` — before starting non-trivial work
- `skills/delivery-review-gates/SKILL.md` — before claiming work is complete
- `skills/assetization-closeout/SKILL.md` — after repeated or valuable work
- `templates/cron/weekly-operating-review.md` — when wiring weekly governance review
- `templates/cron/monthly-operating-audit.md` — when wiring monthly doctrine audit
- `templates/review/task-closeout-template.md` — when standardizing delivery closeout

## What this package is trying to install

This package installs a governance model, not a new execution stack.

The target shape is:
- a **compressed runtime layer** with high-frequency principles
- a **canonical full charter** kept outside the always-loaded prompt
- **governance skills** for start, closeout, and assetization
- **scheduled review prompts** for weekly and monthly correction
- clean separation between doctrine, memory, task state, and assets

## Adoption rules

1. Do **not** replace a mature planning / coding / research / debugging stack just because this repo exists.
2. Keep the always-loaded layer short; do not stuff the full doctrine into runtime context.
3. Copy or adapt the host-facing files deliberately; do not blindly overwrite stronger local files.
4. Put stable facts in memory, active execution in task state, and reusable workflows in skills/templates.
5. When in doubt, prefer the smallest useful adoption layer.

## If you are asked to adopt this repo

Your minimum useful output should be a concrete mapping like:
- runtime layer: what from `SOUL.md` gets loaded
- charter layer: where `docs/operating-doctrine.md` is referenced
- skill layer: which governance skills get installed or emulated
- review layer: how `templates/cron/*` will run or be performed manually
- memory layer: what stable facts belong there
- task-state layer: what remains execution state only

Then:
1. choose the smallest viable adoption profile: minimum / standard / full
2. preserve the host's existing strong execution workflows
3. run the smoke test from `docs/implementation-guide.md`

## Anti-patterns

Do not:
- turn this repo into a giant always-loaded prompt
- treat README as the only doctrine file
- copy the full charter into memory
- duplicate existing strong execution workflows just to “use the kit more”
- add recurring reviews without a clear output contract

## Success condition

A good adoption should make the target agent system:
- more budget-aware
- more verification-driven
- more asset-forming
- easier for another agent to understand and maintain
