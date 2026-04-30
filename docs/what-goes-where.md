# What Goes Where

This is the shortest placement guide in the repository.

Use it when you already understand the doctrine but need a fast answer for **where each kind of content should live**.

## Doctrine

Put in long-form docs when the content defines:
- mission
- north star
- iron laws
- leadership principles
- KPI rationale
- layering philosophy

Best carrier:
- `docs/`

Do not put full doctrine in:
- memory
- skills
- runtime prompt

---

## Runtime Principles

Put in soul/profile/system prompt when the content should influence live decisions frequently and can be compressed to a few stable lines.

Examples:
- customer value first
- token is budget
- no concrete output means not finished
- prefer assetization over repeated one-off effort

Best carrier:
- `templates/soul/`
- framework-specific runtime config

Do not put:
- KPI tables
- long explanations
- adoption playbooks

---

## Governance Workflows

Put in skills when the content has:
- trigger conditions
- repeatable judgment steps
- clear use and non-use cases

Examples:
- should this work start?
- what proves completion?
- should this result become an asset?

Best carrier:
- `skills/`

Do not use governance skills to replace planning, coding, debugging, or execution review workflows your framework already has.

---

## Recurring Review

Put in cron when the content is periodic governance rather than per-task behavior.

Examples:
- weekly operating review
- monthly doctrine audit

Best carrier:
- `templates/cron/`
- framework-native cron or scheduler

Do not use cron for:
- heavy execution pipelines by default
- high-side-effect autonomous actions
- fake daily reporting with no audience

---

## Durable Facts

Put in memory when the content is a stable fact about:
- the core customer
- the environment
- durable preferences
- long-lived constraints

Best carrier:
- framework-native memory system

Do not put in memory:
- the full doctrine
- long workflows
- task-local state
- KPI frameworks

---

## Task State

Put in task state when the content is about active execution.

Examples:
- what is being worked on now
- current status
- blockers
- next action
- verification target

Best carrier:
- framework-native todo/task board/plan files

Do not confuse task state with doctrine or memory.

---

## Assets

Turn outputs into assets when repeated future leverage is likely.

Examples:
- skills
- scripts
- SOPs
- templates
- docs
- cron jobs

Question to ask:
- Will capturing this now reduce future token, time, or error cost?

---

## Rule of Thumb

- doctrine explains
- soul biases
- skills gate
- cron reviews
- memory remembers facts
- task state tracks active work
- assets compound value
