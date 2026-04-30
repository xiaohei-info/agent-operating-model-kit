# AGENTS.md

## Purpose of This Repository

This repository packages a reusable **agent operating model kit** for single-customer micro AI organizations.

It is a **governance repository**, not a replacement execution stack.

Contributors and coding agents working here should preserve that boundary.

## Core Maintenance Rules

### 1. Doctrine-first changes
If a proposed change alters mission, north star, iron laws, leadership principles, KPI semantics, or layering boundaries, update the doctrine docs first before changing templates or skills.

### 2. Do not rebuild existing execution frameworks here
This repo should not grow into a competing execution framework.

Avoid adding:
- generic coding workflows that existing agent frameworks already do well
- redundant planning/debugging/research skills
- framework-specific runtime hacks in the core doctrine layer

Prefer adding:
- governance checklists
- review gates
- assetization logic
- adoption documentation
- reference templates

### 3. Keep the layering clean
Use the intended carriers:
- doctrine and rationale -> `docs/`
- compact runtime guidance -> `templates/soul/`
- governance workflows -> `skills/`
- recurring review prompts -> `templates/cron/`
- examples and reference rollouts -> `examples/`

Do not put long doctrine into skills. Do not put KPI tables into soul templates.

### 4. Treat skills as governance skills
Skills in this repo should answer questions like:
- should this work start?
- what proves completion?
- should this become an asset?

They should not become broad execution skills unless a truly missing governance gap justifies it.

### 5. Prefer portability over local convenience
Do not hard-code:
- private local paths
- user-specific secrets
- one-machine assumptions
- one-framework assumptions in doctrine files

Framework-specific guidance belongs under `docs/integrations/` or `examples/`.

### 6. Keep examples explicit but non-authoritative
Examples should help operators adopt the model, but they should be presented as reference implementations, not as the only valid setup.

### 7. Use concise, inspectable writing
Optimize for:
- clear boundaries
- low ambiguity
- portable terminology
- explicit non-goals

Avoid:
- manifesto bloat
- vague slogans without operational meaning
- duplicating the same principle across many files without adding value

## Recommended Change Flow

For meaningful updates:
1. update or add doctrine/rationale in `docs/`
2. update any affected templates
3. update any affected governance skills
4. update README if adoption guidance changes
5. verify the repository still reads as a coherent kit rather than a loose document dump

## Verification Expectations

Before claiming repo work is complete, verify:
- the file structure matches the documented layering
- README references existing files
- example and template paths are valid
- any new skill has a clear trigger condition and stays within governance scope

## Non-Goals

This repo is not trying to:
- define a universal agent personality
- mandate a specific multi-agent topology
- replace Hermes, OpenClaw, Claude Code, or other execution substrates
- force a heavy task board or KPI bureaucracy by default

## Design Standard

A good contribution makes the operating model:
- easier to understand
- easier to adopt
- harder to misuse
- more compatible with existing agent ecosystems
