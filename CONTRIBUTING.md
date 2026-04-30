# Contributing

Thank you for contributing to **Agent Operating Model Kit**.

This project is a governance-layer package for single-customer micro AI organizations. The quality bar here is different from a normal agent feature repo: the job is not to add more execution complexity, but to make the operating model clearer, more portable, and more reusable.

## Before You Change Anything

Read these first:
- `README.md`
- `AGENTS.md`
- `docs/operating-doctrine.md`
- `docs/layering.md`
- `docs/adoption-playbook.md`

If your change touches mission, north star, iron laws, KPI semantics, or layering boundaries, update doctrine docs first.

## What Kinds of Contributions Are Welcome

### Good contributions
- clearer doctrine wording
- better adoption guidance
- stronger governance checklists
- more portable examples
- framework-specific integration docs under `docs/integrations/`
- cron review prompts
- better soul/runtime compression templates
- small governance skills with clear trigger conditions

### Contributions that need extra scrutiny
- new skills that overlap with existing execution frameworks
- anything that turns this repo into a full agent framework
- heavy task board systems
- local-environment assumptions in core docs
- KPI expansion that adds bureaucracy without leverage

## What This Repo Should Not Become

Do not turn this repository into:
- a generic coding assistant framework
- a personality pack
- a giant prompt dump
- a replacement for Hermes / OpenClaw / Claude Code / Codex execution layers
- a one-off local setup archive

## Layer-Aware Contribution Rules

### Docs (`docs/`)
Use for:
- doctrine
- rationale
- KPI design
- layering explanations
- adoption playbooks
- framework integration notes

### Skills (`skills/`)
Use for:
- governance gates
- review gates
- assetization decisions
- repeatable judgment workflows

Do **not** use repo skills to duplicate planning, coding, debugging, or general research workflows already handled better elsewhere.

### Templates (`templates/`)
Use for:
- soul/profile excerpts
- cron prompts
- review templates

Templates should be copyable and compact.

### Examples (`examples/`)
Use for:
- reference implementations
- illustrative setups
- concrete but non-authoritative adoption paths

Examples should help operators adopt the model without implying there is only one valid deployment.

## Change Process

For meaningful changes, prefer this order:
1. update doctrine or rationale in `docs/` if needed
2. update affected templates
3. update affected governance skills
4. update README if navigation or adoption guidance changed
5. verify file references and structure

## Writing Standards

Optimize for:
- clarity over flourish
- compactness over manifesto bloat
- explicit boundaries over implied intent
- portable language over local jargon
- real operational meaning over motivational slogans

When possible, explain:
- what the artifact is for
- when to use it
- when not to use it
- how it composes with an existing framework

## Verification Checklist

Before claiming your contribution is ready, verify:
- referenced files actually exist
- README navigation is still accurate
- examples still match the documented layering model
- new skills have clear trigger conditions
- new content does not violate the governance-vs-execution boundary
- no local private paths leaked into generic doctrine files

## Pull Request / Review Expectations

A good contribution should make the operating model:
- easier to understand
- easier to adopt
- harder to misuse
- more compatible with existing agent ecosystems

If a change adds complexity, it should justify why the extra complexity buys real leverage.
