# Implementation Guide

This document explains how to land the operating model in another agent environment without replacing an execution stack that already works.

## Core Rule

This repository is a governance package, not a replacement execution substrate.

It tells operators and agents **what to add where**, and provides **thin host-facing files** that can be adapted deliberately.

Do not blindly copy everything into the host profile. Instead, map the pieces to the right layers.

## How to adopt

### 1. Runtime profile / system prompt layer

Install the compressed operating charter from `SOUL.md`.

Keep it small:
- customer value first
- token is budget
- no concrete output means not finished
- no verification means not complete
- proactively close gaps, but do not expand scope

Do not put:
- the full doctrine
- KPI definitions
- long adoption instructions
- recurring review prompts

### 2. Charter layer

Keep the canonical full charter in `docs/operating-doctrine.md`.

Reference it when:
- aligning on model changes
- auditing whether runtime / skills / cron have drifted from doctrine
- deciding what belongs where
- explaining the rationale to humans

Do not load the full charter into every session unless the host explicitly requests it.

### 3. Governance skills layer

Adopt the three governance skills from this repository:
- `operating-gates` — gate before starting non-trivial work
- `delivery-review-gates` — gate before claiming completion
- `assetization-closeout` — gate after valuable/repeated work

These skills govern execution, not replace it. Use them to enforce value, budget, scope, and verification checks.

### 4. Recurring review layer

Use the host’s cron / scheduler / heartbeat system to run:
- `templates/cron/weekly-operating-review.md`
- `templates/cron/monthly-operating-audit.md`

These prompts enforce recurring governance.

### 5. Memory layer

Use the host’s memory system only for stable facts:
- the core customer identity
- durable environment constraints
- long-lived user preferences

Do not put the doctrine, procedures, or long workflows into memory.

### 6. Task-state layer

Use the host’s task board, todo, or plan files for:
- current work
- blockers
- next actions
- verification targets

Task state should track active execution, not permanent governance.

### 7. Host-facing entry files

This repo now ships thin host-facing files that you can adapt deliberately:
- `AGENTS.md` — operational loader / read router
- `SOUL.md` — compressed runtime charter

You can:
- use them directly if the host environment accepts such files
- merge them into existing host files if the host already has stronger local versions
- rewrite them for your framework if the conventions differ

Do **not** blindly overwrite stronger local entry files.

## Recommended rollout order

1. Read `README.md`, `AGENTS.md`, and `SOUL.md`.
2. Read `docs/operating-doctrine.md` to understand the full charter.
3. Install the compressed runtime principles.
4. Install the governance skills.
5. Install the recurring review prompts.
6. Map each component to the correct host surface.
7. Verify that the package did not replace strong execution workflows.

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
- mandate a specific multi-agent topology
- replace a working execution framework
- force one file structure onto every host environment
- add bureaucracy for its own sake

## Verification

After adopting:
- `README.md` should remain the primary landing and onboarding doc
- `AGENTS.md` should serve as the operational loader
- `SOUL.md` should serve as the compressed runtime charter
- `docs/operating-doctrine.md` should hold the full canonical doctrine
- skills should govern execution rather than replace it
- recurring reviews should run with clear output contracts
- memory should stay compact
- task state should stay execution-focused