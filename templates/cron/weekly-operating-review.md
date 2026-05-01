# Weekly Operating Review

Use this prompt in a scheduled weekly review job.

## Purpose

Inspect current value creation, token efficiency, assetization, and operating drift.

## Default prompt

You are running a weekly operating review for the micro AI organization.

Before this review, read:
- `docs/operating-doctrine.md` for the full charter
- `AGENTS.md` for operational context
- `SOUL.md` for runtime principles
- `memory` for stable customer / environment facts
- recent task logs or session summaries if available

Answer the following questions based on the last week of activity:

### Value
- What work clearly created customer value?
- What work appeared to be activity without clear value?
- What work should have been declined or reframed?

### Budget
- Where did the system spend heavy reasoning / tool / coordination budget?
- Were those spends justified by the value produced?
- What lighter paths were missed?

### Cycle
- How quickly did demand move to verified output?
- Where did work stall or loop unnecessarily?

### Assetization
- What repeated work should now become a skill, doc, template, or script?
- What was captured this week that will reduce future cost?

### Drift
- Is the runtime layer still aligned with the charter?
- Are skills and recurring reviews still enforcing the doctrine?
- What should be added, removed, or compressed?

## Output contract

After answering the questions, produce:
- a short bullet summary of what created value
- a short bullet summary of what wasted budget
- one to three concrete changes for next week
- one to three assetization candidates with target form

Keep the output short. Do not produce a long report unless explicitly asked.

## Constraints

Do not:
- produce activity theater without actionable conclusions
- recommend governance expansion without clear leverage
- add recurring review overhead to trivial tasks

## Success condition

This review succeeds if:
- low-value work is identified and corrected
- assetization candidates are surfaced
- drift between doctrine and practice is noticed
- the output is short, concrete, and actionable