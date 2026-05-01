# Implementation Guide

This document explains how to land the operating model in another agent environment without replacing an execution stack that already works.

## Core Rule

This repository is a governance package, not a replacement execution substrate.

Do not blindly copy everything into the host profile. Instead, identify what each file is for and map only the surfaces the host environment actually needs.

## First distinction: artifact types

This repository contains several different kinds of packaging surfaces.

### 1. Core artifacts
These carry the doctrine and reusable governance logic itself.

Examples:
- `docs/operating-doctrine.md`
- `skills/*/SKILL.md`
- `templates/review/task-closeout-template.md`

### 2. Integration surfaces
These help the host map the package into runtime behavior.

Examples:
- `AGENTS.md`
- `SOUL.md`
- `MEMORY.md`
- `docs/integrations/<framework>.md`

### 3. Operational surfaces
These support recurring or ongoing governance.

Examples:
- `templates/cron/*.md`

### 4. Deployment guides
These explain how the reusable pieces should be installed or adapted.

Examples:
- `skills/README.md`
- `templates/cron/README.md`
- this document

These categories cooperate, but they are not interchangeable.

## How to map the package into a host stack

### A. Canonical doctrine
Keep the full charter in a durable reference surface.

Recommended source:
- `docs/operating-doctrine.md`

Use it when:
- aligning on model changes
- auditing drift
- deciding what belongs in runtime vs skills vs operations
- explaining the rationale to humans

Do not load the full charter into every session unless the host explicitly needs it.

### B. Reusable governance skills
Install the governance skills only where the host benefits from reusable judgment or workflow enforcement.

Recommended source:
- `skills/operating-gates/SKILL.md`
- `skills/delivery-review-gates/SKILL.md`
- `skills/assetization-closeout/SKILL.md`
- `skills/README.md`

Use them for:
- start-of-work gating
- completion / closeout review
- assetization decisions

These skills govern execution. They do not replace the host framework's planning, coding, research, debugging, or verification stack.

### C. Runtime guidance
Some hosts need a compressed, always-loaded runtime surface. Some do not.

Recommended source:
- `SOUL.md`

Use it when the host has a clear runtime prompt / system prompt / profile surface.

Keep it small:
- customer value first
- token is budget
- no concrete output means not finished
- no verification means not complete
- proactively close gaps, but do not expand scope for activity's sake

Do not put into the runtime surface:
- the full doctrine
- long KPI definitions
- large implementation guides
- recurring review prompts

### D. Agent-facing routing surface
Some hosts benefit from a thin operational loader that tells an adopting agent what to read first.

Recommended source:
- `AGENTS.md`

Use it when the host supports a dedicated agent-facing entry file or equivalent routing document.

If the host already has a stronger local runtime/entrypoint file, merge or adapt deliberately rather than blindly overwriting it.

### E. Memory boundaries
Some hosts expose durable memory. If they do, define what belongs there before storing anything.

Recommended source:
- `MEMORY.md`

In short:
- memory is for stable facts and accepted conventions
- memory is not for doctrine, long procedures, or active task state

### F. Scheduled / recurring governance
Only install recurring governance surfaces if the host has an actual scheduler, cron system, heartbeat, or durable background execution path.

Recommended source:
- `templates/cron/weekly-operating-review.md`
- `templates/cron/monthly-operating-audit.md`
- `templates/cron/README.md`

Use them for:
- weekly operating review
- monthly doctrine audit

Do not treat scheduled prompts as mandatory for every adoption. They are optional operational surfaces.

### G. Task state
Task state usually belongs to the host's existing task board, todo system, issue tracker, or planning files.

Recommended rule:
- keep active execution state in the host's task system
- do not confuse task state with doctrine, memory, or reusable skills

## Package anatomy vs rollout order

Two different questions must stay separate:

- **Package anatomy**: what kinds of artifacts the repository ships
- **Rollout order**: in what sequence the host should adopt them

Do not confuse them.

A repository may ship runtime surfaces, memory guidance, scheduled prompts, and framework adapters, but a specific host may only need some of them.

## Recommended rollout order

1. Read `README.md`.
2. Read `AGENTS.md` for the thin routing view.
3. Read `docs/operating-doctrine.md` for the canonical model.
4. Decide which reusable governance skills the host should install.
5. Decide whether the host needs compressed runtime guidance from `SOUL.md`.
6. Decide whether the host needs durable memory boundaries from `MEMORY.md`.
7. Decide whether the host has a real scheduler and therefore should adopt `templates/cron/*`.
8. Map each selected surface into the correct host carrier.
9. Verify that strong local execution workflows were preserved.

## Decision questions for adopters

Before installing a surface, ask:
- Is this the skill artifact itself, or just a deployment/integration aid?
- Does the host already have an equivalent surface?
- Does the host actually need this surface, or is it optional here?
- Would installing this improve governance, or just add ceremony?
- Does this belong in runtime, memory, scheduled review, or reusable skill logic?

## Success criteria

A successful adoption should result in:
- fewer low-value tasks being started
- more evidence-based completion claims
- more repeated work becoming reusable assets
- stronger budget awareness
- no unnecessary replacement of existing execution workflows

## Non-goals

This repository is not trying to:
- define a universal agent personality
- mandate one fixed repository taxonomy for all skill projects
- force every host to adopt every surface
- replace a working execution framework
- add bureaucracy for its own sake

## Verification

After adopting:
- `docs/operating-doctrine.md` should remain the canonical doctrine source
- installed skills should govern execution rather than replace it
- runtime guidance, if adopted, should stay compressed
- memory, if used, should stay compact and fact-like
- recurring reviews, if adopted, should run with clear output contracts
- platform-specific docs should remain edge integrations, not the core story
