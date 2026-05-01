# Implementation Guide

This document explains how to land the operating model in another agent environment without replacing an execution stack that already works.

## Core rule

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

## Capability-based landing algorithm

Land the package by checking what the host can actually support.

### Step 1. Check for a durable doctrine surface
If the host has anywhere to keep reference documents:
- store or reference `docs/operating-doctrine.md`
- use it as the canonical source of truth

If not:
- keep the doctrine outside the runtime prompt anyway
- reference it from a file store, repo checkout, or operator notes instead of compressing it into runtime by force

### Step 2. Check for a runtime guidance surface
If the host has a system prompt, runtime profile, or equivalent:
- map `SOUL.md` there in compressed form

If not:
- use `SOUL.md` as a manual pre-read for non-trivial work
- do not expand the doctrine into ad hoc long prompts to compensate

### Step 3. Check for a reusable skill surface
If the host supports reusable skills, slash commands, macros, or procedural cards:
- install the three governance skills directly

If not:
- emulate them manually as explicit checklists at the correct moments:
  - before non-trivial work → `operating-gates`
  - before claiming done → `delivery-review-gates`
  - after repeated/high-value work → `assetization-closeout`

### Step 4. Check for durable memory
If the host supports persistent memory:
- apply `MEMORY.md`
- store only compact durable facts

If not:
- skip memory as a system feature
- keep durable facts in explicit docs or project notes rather than inventing a fake memory layer

### Step 5. Check for scheduling
If the host supports cron, timers, scheduled jobs, or recurring background execution:
- install the weekly and monthly review prompts

If not:
- run the same reviews manually on a calendar rhythm
- keep the prompts as operating checklists rather than abandoning recurring review entirely

### Step 6. Check for task state
If the host already has tasks, issues, todos, or planning notes:
- use that for active execution state

If not:
- do not overload memory or doctrine to compensate
- use a lightweight local task list or session-scoped plan file

### Step 7. Preserve strengths already present
If the host already has strong planning, coding, research, debugging, verification, or routing:
- keep them
- add only the governance pieces this package provides

The goal is composition, not replacement.

## Adoption profiles

Use the smallest profile that produces real leverage.

### Minimum profile
Use when:
- the host is simple
- the operator mainly wants better judgment and closeout quality
- there is limited ability to install extra surfaces

Install:
- `docs/operating-doctrine.md` as canonical reference
- `SOUL.md` or equivalent compressed runtime guidance if possible
- manual use of the three governance skills as checklists

Expected improvement:
- better framing
- stronger closeouts
- less scope drift

### Standard profile
Use when:
- the host can load reusable skills or equivalent procedural assets
- the operator wants repeatable governance with low overhead

Install:
- everything in minimum profile
- the three governance skills as reusable assets
- `MEMORY.md` if the host supports persistent memory

Expected improvement:
- repeatable start / closeout / assetization gates
- better cross-session consistency
- reduced operator steering

### Full profile
Use when:
- the host also supports scheduling or recurring background execution
- the operator wants ongoing drift correction and governance maintenance

Install:
- everything in standard profile
- weekly operating review
- monthly doctrine audit

Expected improvement:
- better ongoing calibration
- reduced doctrine drift
- stronger assetization over time

## Package anatomy vs rollout order

Two different questions must stay separate:

- **Package anatomy**: what kinds of artifacts the repository ships
- **Rollout order**: in what sequence the host should adopt them

Do not confuse them.

A repository may ship runtime surfaces, memory guidance, scheduled prompts, and framework adapters, but a specific host may only need some of them.

## Recommended rollout order

1. Read `README.md`.
2. Read `docs/operating-doctrine.md` for the canonical model.
3. Read `docs/implementation-guide.md` for the landing algorithm and adoption profiles.
4. Read `AGENTS.md` if a thin routing view would help the host mapping.
5. Choose an adoption profile: minimum, standard, or full.
6. Map `SOUL.md` if the host has a runtime guidance surface.
7. Install or emulate the governance skills.
8. Apply `MEMORY.md` if the host supports persistent memory.
9. Install or emulate recurring reviews if the host supports scheduling.
10. Map each selected surface into the correct host carrier.
11. Verify that strong local execution workflows were preserved.

## Worked example: host-neutral landing

Assume a host environment with:
- one system prompt surface
- reusable skill loading
- persistent memory
- no scheduler

A correct landing would look like:
- doctrine → keep `docs/operating-doctrine.md` as reference material outside the runtime prompt
- runtime guidance → load the compressed principles from `SOUL.md`
- governance skills → install the three skills as on-demand gates
- memory → apply `MEMORY.md` so doctrine and procedures do not leak into durable memory
- recurring review → keep the weekly/monthly prompts available, but run them manually because no scheduler exists
- task state → continue using the host's existing task mechanism

A wrong landing would look like:
- copying the full doctrine into runtime
- storing governance rules in memory
- replacing the host's execution workflows with the governance skills
- skipping review cadence entirely because no scheduler exists

## Decision questions for adopters

Before installing a surface, ask:
- Is this the skill artifact itself, or just a deployment/integration aid?
- Does the host already have an equivalent surface?
- Does the host actually need this surface, or is it optional here?
- Would installing this improve governance, or just add ceremony?
- Does this belong in runtime, memory, scheduled review, or reusable skill logic?

## Post-install smoke test

After landing the package, verify these behaviors:

### 1. Start-of-work behavior
On a non-trivial task, the host should be able to answer:
- what value the task creates
- what deliverable will count as success
- what the verification method is
- whether a lighter path exists

### 2. Closeout behavior
Before saying work is done, the host should be able to state:
- what changed or was produced
- what fresh evidence supports completion
- what remains limited or unverified
- what next step is appropriate

### 3. Assetization behavior
After repeated or high-value work, the host should be able to decide:
- whether a reusable asset is justified
- what the correct carrier is
- why that carrier is better than leaving the learning in raw conversation

### 4. Boundary behavior
The host should keep:
- doctrine in doctrine
- runtime guidance in the runtime surface
- procedures in skills or docs
- stable facts in memory only when memory exists
- active work in task state

### 5. Preservation behavior
Existing strong execution workflows should remain intact. The package should govern them, not replace them.

If these five checks fail, the adoption is incomplete or mis-mapped.

## Failure modes and corrections

### Failure mode: the doctrine was injected into every session
Correction:
- move long-form doctrine out of runtime
- keep only compressed principles in `SOUL.md`

### Failure mode: the host has no skill loader and the package was abandoned
Correction:
- keep the doctrine and runtime guidance
- emulate governance skills manually at the right moments

### Failure mode: memory became a doctrine dump
Correction:
- move long rules back into doctrine, skills, or templates
- keep only compact durable facts in memory

### Failure mode: recurring review became ceremony
Correction:
- shorten output contracts
- require concrete actions or deletions
- reduce cadence if the review does not produce leverage

### Failure mode: the package displaced strong local execution flows
Correction:
- restore the host's native planning/execution workflows
- keep only the governance overlay from this kit

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
