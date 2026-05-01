# Monthly Doctrine Audit

Use this prompt in a scheduled monthly audit job.

## Purpose

Compare the installed runtime layer, skills, and recurring reviews against the canonical charter.

Detect drift, duplication, stale instructions, and weak surfaces.

## Preflight

Before this audit, gather as much of the following as the host can provide:
- `docs/operating-doctrine.md` for the full charter
- `AGENTS.md` for the operational loader if present
- `SOUL.md` for the compressed runtime charter
- `skills/` for governance skills if installed
- `templates/cron/` for recurring reviews if installed
- durable memory or local environment notes if available
- recent weekly operating review outputs if available

If some surfaces do not exist in the host, continue with the best available evidence and state what was missing.

## Default prompt

You are running a monthly doctrine audit for the micro AI organization.

Answer the following questions:

### Charter alignment
- Does the runtime layer still reflect the compressed charter from `SOUL.md`?
- Has any local configuration drifted away from the doctrine?
- Are the iron laws still enforced in practice?

### Skill mapping
- Are governance skills still governing the correct points (start, closeout, assetization)?
- Have execution workflows grown around governance in ways that contradict the charter?
- Are skills thin and reusable, or have they become heavy execution replacements?

### Review cadence
- Are weekly and monthly reviews running with clear output contracts?
- Are reviews producing actionable change or just activity reports?

### Packaging
- Is the full charter still canonical and separate from the runtime layer?
- Are always-loaded files staying short?
- Are framework-specific integrations still at the edges?

### Drift sources
- What instructions or behaviors have appeared that are not supported by the doctrine?
- What old instructions or behaviors should be removed or compressed?

## Drift categories

Classify notable issues as one of:
- **Clarify doctrine** — the charter is too thin or ambiguous
- **Compress runtime** — the runtime guidance is too long, too weak, or out of sync
- **Strengthen skill** — a governance gate is missing, stale, or inconsistent
- **Retune recurring review** — the weekly/monthly cadence is not creating leverage
- **Delete clutter** — an artifact exists but no longer justifies itself

## Output contract

After answering the questions, produce:
- one to three items that should move between surfaces (runtime / skill / review / doc)
- one to three items that should be deleted or compressed
- one to three items that should be clarified in the charter
- a short summary of overall alignment status

For each item, state the target carrier explicitly.

Keep the output short. Do not produce a long audit report unless explicitly asked.

## Constraints

Do not:
- expand the doctrine for its own sake
- add governance layers without clear leverage
- recommend complex refactors if simple deletion or compression is sufficient

## Success condition

This audit succeeds if:
- drift between doctrine and practice is identified
- packaging hygiene is restored
- unnecessary complexity is surfaced for removal
- the output is short, concrete, and actionable