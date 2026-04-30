# Adoption Playbook

This playbook describes a safe sequence for adopting the operating model without colliding with an existing agent framework.

## Adoption Principle

Adopt governance before rebuilding execution.

If you already have working skills, tools, cron jobs, or subagent systems, do **not** replace them just to conform to this model. Instead, add doctrine and gates first, then tighten review cadence, then create assets where repetition proves value.

## Adoption Maturity Levels

This playbook uses Levels 0–5. Lower levels are intentionally useful on their own; do not rush upward unless the lower levels are already stable.

## Level 0: Read-Only Doctrine

### Goal
Understand the model and align on terminology.

### Do
- read `docs/operating-doctrine.md`
- read `docs/layering.md`
- decide whether your use case is actually a single-customer operating model

### Do not
- rewrite runtime prompts yet
- build new skills yet
- change cron or task systems yet

---

## Level 1: Runtime Principles

### Goal
Inject a compact doctrine excerpt into the live agent so decisions begin to drift toward the model.

### Do
- add a short principle excerpt to soul/profile/system prompt
- keep it compact and stable

### Success signal
- the agent starts naturally optimizing for customer value, budget awareness, deliverables, and assetization

---

## Level 2: Governance Gates

### Goal
Enforce the doctrine at key decision points.

### Do
- adopt `operating-gates`
- adopt `delivery-review-gates`
- adopt `assetization-closeout`

### Success signal
- fewer low-value tasks start
- completion claims become evidence-backed
- more outputs become reusable assets

---

## Level 3: Recurring Review

### Goal
Make the model inspectable and adjustable over time.

### Do
- set up a weekly operating review
- set up a monthly doctrine audit
- use company-level KPIs only at first

### Success signal
- you can identify where budget was wasted, where cycle time dragged, and where assetization opportunities were missed

---

## Level 4: Reference Integration

### Goal
Create framework-specific guidance so others can adopt the model with less ambiguity.

### Do
- document what goes into soul vs skill vs cron vs memory
- show how the model composes with existing framework skills and tooling
- publish examples rather than hard-coding assumptions

### Success signal
- another operator can follow the repo and reproduce a working setup in their environment

---

## Level 5: Standalone Profile or Agent Packaging

### Goal
Bundle the model as a portable operating mode.

### Do
- package doctrine + runtime principles + governance skills + cron templates + adoption docs
- keep execution substrate modular

### Warning
Do not package this as a new agent identity until the doctrine and integration story are already stable.

## Adoption Sequence Summary

1. doctrine
2. runtime principle excerpt
3. operating gates
4. recurring KPI review
5. framework-specific examples
6. optional standalone packaging

## Practical Landing Guidance

- Lowest-risk start: adopt Levels 0 and 1.
- Meaningful behavior change without structural disruption: adopt through Level 2.
- Inspectable and self-correcting operation: adopt through Level 3.
- Shareable or portable operating mode: adopt through Levels 4 and 5.

Do not add packaging, cron, or heavy review ceremony before the doctrine and governance gates are already helping in real work.

## Common Failure Modes

### Failure Mode 1: Turning the model into ceremony
Symptoms:
- long checklists for trivial tasks
- too many reviews for low-risk work
- too much time spent reporting rather than delivering

Fix:
- reserve heavier governance for higher-value or higher-risk work

### Failure Mode 2: Rebuilding existing execution skills
Symptoms:
- duplicating planning, coding, review, or research workflows that already work

Fix:
- keep this repository as a governance overlay

### Failure Mode 3: Overfitting to one framework
Symptoms:
- local paths, private assumptions, or one framework's file system leak into the model core

Fix:
- keep doctrine generic and integrations explicit but separate

### Failure Mode 4: KPI theater
Symptoms:
- scoring everything while learning nothing

Fix:
- use KPI review only to improve decisions and structure, not to generate dashboards for their own sake
