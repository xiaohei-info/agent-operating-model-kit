# Contributing

Thank you for contributing to **Agent Operating Model Kit**.

This repository is a **governance-layer package** for single-customer micro AI organizations. Contributions should make the model easier to understand, easier to adopt, and harder to misuse.

## Before You Change Anything

Read:
- `README.md`
- `docs/implementation-guide.md`
- `docs/integrations/hermes.md` if your change touches the Hermes reference path

## Good Contributions

- clearer charter wording
- stronger portability guidance
- tighter governance skills
- better recurring review prompts
- simpler adoption guidance
- cleaner examples that reduce ambiguity

## Contributions That Need Extra Scrutiny

- anything that turns this repo into a full execution framework
- any host-framework entry files intended to be copied over local ones
- heavy task-board systems
- KPI expansion that adds bureaucracy without leverage
- local or user-specific assumptions in core docs

## Host-facing entry files

This repository now ships thin host-facing files that another agent can adapt deliberately:
- `AGENTS.md`
- `SOUL.md`

These are intended to be:
- used directly if the host environment accepts them
- merged into stronger local files if the host already has mature content
- rewritten for the target framework if conventions differ

Do **not** blindly overwrite stronger local entry files. The goal is deliberate adaptation, not accidental replacement.

## Change Rules

For meaningful changes:
1. update `README.md` if the charter or main adoption path changes
2. update `docs/implementation-guide.md` if placement guidance changes
3. update governance skills if the reusable workflow changes
4. update integration docs only if framework-specific advice must change
5. verify the repo still reads like a compact kit rather than a document dump

## Verification Checklist

Before claiming work is ready, verify:
- the main README still functions as the primary landing doc
- `AGENTS.md` serves as a thin operational loader
- `SOUL.md` serves as a compressed runtime charter
- `docs/operating-doctrine.md` remains canonical and separate
- file references are valid
- host-facing files were added deliberately, not blindly
- governance skills still stay in governance scope
- recurring review prompts have clear output contracts
- the package became simpler or more useful, not just larger

## Design Standard

A good contribution makes the package:
- more portable
- more legible
- less repetitive
- less framework-dependent at the core
- easier for another agent to adopt in one pass
