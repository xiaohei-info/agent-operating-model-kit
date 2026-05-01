# Hermes Reference Integration

This file is a **reference edge integration**, not the core of the kit.

## Principle

Use the operating model as a governance overlay on top of Hermes.

Do not replace Hermes' execution substrate if it already works well.

## Mapping

### Runtime layer

Inject the compressed charter from `SOUL.md` into the Hermes profile / prompt layer.

Do not inject the full doctrine into every session. Keep the runtime layer small.

Example principles to load:
- customer value first
- token is budget
- no concrete output means not finished
- no verification means not complete

### Charter layer

Keep `docs/operating-doctrine.md` as the canonical reference.

Read it when:
- aligning on model changes
- auditing runtime / skills / cron for drift
- explaining governance rationale

### Skills layer

Adopt the governance skills from this repository:
- `skills/operating-gates/SKILL.md`
- `skills/delivery-review-gates/SKILL.md`
- `skills/assetization-closeout/SKILL.md`

You can:
- symlink or copy them under `~/.hermes/skills/`
- or adapt them into Hermes-native skill format if conventions differ

Keep using Hermes' own execution skills for planning, coding, research, debugging, and verification.

### Review cadence

Use Hermes `cronjob` or equivalent scheduler to run:
- `templates/cron/weekly-operating-review.md` — weekly governance review
- `templates/cron/monthly-operating-audit.md` — monthly doctrine audit

Wire these as cron jobs with:
- a clear prompt
- an output target
- a delivery channel

### Memory layer

Use Hermes `memory` for stable customer and environment facts only.

Do not put the doctrine or long workflows into memory.

### Task state

Use Hermes `todo` or plan files for active execution state.

### Host-facing entry files

This repo now ships:
- `AGENTS.md`
- `SOUL.md`

You can:
- use them directly in the Hermes profile if desired
- or merge them into existing Hermes prompt / profile files if Hermes already has strong local content

Do not blindly overwrite stronger Hermes defaults.

## What Not to Do

Do not:
- copy the entire repository into `~/.hermes`
- replace Hermes profile files blindly
- turn governance skills into broad execution skills
- duplicate Hermes execution workflows if they already work
- inject the full doctrine into every session

## Success Condition

A good Hermes adoption should:
- improve budget discipline
- improve completion quality
- improve assetization
- preserve the strengths of Hermes' execution stack
- keep the runtime layer compact

## Verification

After wiring this into Hermes:
- the compressed charter should load in the runtime profile
- the full charter should be referenced, not always-loaded
- governance skills should be available
- weekly and monthly review jobs should be scheduled
- memory should stay compact and fact-based
- execution workflows should remain unchanged if they were already strong