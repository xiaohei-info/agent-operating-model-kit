# MEMORY.md

Guidance on what durable facts belong in long-term memory when adopting this kit.

## Purpose

This layer defines memory boundaries so another agent does not duplicate doctrine, runtime principles, or governance rules in memory.

Memory is for stable facts that reduce future steering. It is not a storage layer for doctrine text.

## What belongs in memory

- user preferences and recurring corrections
- stable environment facts (OS, installed tools, project structure)
- conventions and workflows that proved durable across sessions
- corrections like "don't do X again" or "always check Y before Z"

## What never belongs in memory

- full doctrine or charter text
- runtime principles already carried in `SOUL.md` or `AGENTS.md`
- repeatable governance logic that belongs in skills
- scheduled review prompts that belong in cron
- temporary task state or session-specific decisions

## Layer separation rule

If the same content already lives in:
- `docs/operating-doctrine.md` → do not mirror in memory
- `SOUL.md` → do not mirror in memory
- `AGENTS.md` → do not mirror in memory
- `skills/*/SKILL.md` → do not mirror in memory

Memory should capture what those layers do not: personal preferences, environmental quirks, and hard-to-infer corrections.

## Typical memory entries for this kit

- "User prefers minimal file edits over large refactorings"
- "This environment has an Obsidian vault at /path"
- "User wants doctrine in docs, runtime in SOUL, skills in skills/, review in cron — never in memory"
- "Do not add host-specific runtime entry files unless the host explicitly requests them"

## How to use this file

- when mapping this kit into a host stack, read `MEMORY.md` once to understand memory boundaries
- when writing durable facts, check if they belong in memory or in another layer
- when memory drifts toward doctrine, move that content back to `docs/operating-doctrine.md` or `SOUL.md`