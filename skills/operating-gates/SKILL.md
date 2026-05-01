---
name: operating-gates
description: Use before starting non-trivial work to decide whether the task should consume budget now, what success looks like, and whether a lighter path exists.
version: 0.2.0
author: Agent Operating Doctrine
license: MIT
---

# Operating Gates

## Overview

This skill is a governance gate, not an execution workflow. Use it before starting non-trivial work to avoid spending budget on low-value, underspecified, or over-engineered tasks.

## Use This When

Use when:
- a task is multi-step or non-trivial
- you are about to delegate or spin up heavier execution
- the user request is broad enough that scope or value could drift
- a more expensive model, agent, or tool chain might be used

Do not use for:
- obvious one-step trivial tasks
- tiny formatting changes with no ambiguity

## What counts as non-trivial

Treat work as non-trivial when one or more of these are true:
- it requires three or more meaningful steps
- it affects multiple files, systems, or decisions
- it may trigger external side effects
- it has meaningful ambiguity about value, scope, or method
- it will consume moderate or heavy execution budget
- it could create costly downstream correction if framed badly

## The gates

### 1. Value gate
Answer:
- What customer value will this produce?
- Why is it worth doing now?
- What concrete output would make it successful?

If you cannot answer these, do not expand into execution yet.

### 2. Budget gate
Answer:
- Does this require heavy reasoning, multiple agents, or many tools?
- Is that spend justified by expected value?
- Is there a lighter path that would preserve correctness?

Prefer the lowest-cost path that still achieves a verified result.

### 3. Scope gate
Answer:
- What is in scope?
- What is explicitly out of scope?
- What assumptions are being made?

State assumptions rather than silently expanding the task.

### 4. Output gate
Define before starting:
- deliverables
- verification method
- important risks or side effects

If there is no concrete output or no verification method, the task is not ready for heavier execution.

## Outcome modes

This gate should end in one of four outcomes:

### 1. Proceed
Use when:
- value is clear
- output is concrete
- verification is defined
- budget is proportionate

### 2. Reframe
Use when:
- the task is valuable but too broad
- a smaller path would reach the same outcome
- deliverables or verification need tightening before work starts

### 3. Ask user
Use when:
- a critical assumption is missing
- multiple interpretations differ materially in effort or risk
- the desired output or risk tolerance is unclear

### 4. Decline or do not scale
Use when:
- value is weak or speculative
- the budget is not justified
- the task is not ready for heavier execution
- the work would mainly create activity instead of customer value

## Budget heuristics

### Light path
Usually means:
- one or two direct tool calls
- very small edits
- narrow factual retrieval

### Moderate path
Usually means:
- multi-step work
- explicit framing needed
- moderate review required before closeout

### Heavy path
Usually means:
- many tools, many steps, or many moving parts
- broad research or coordination
- meaningful external side effects or costly failure

Do not move to a heavier path unless the lighter path is clearly insufficient or the expected value/risk justifies it.

## Minimal output schema

For non-trivial tasks, produce a compact framing before execution:
- Goal
- Deliverables
- Verification
- Risks / assumptions
- Outcome mode: proceed / reframe / ask user / decline

## Example strong framing

- Goal: audit whether the repo can be adopted from the link alone
- Deliverables: a prioritized gap list and concrete file-level recommendations
- Verification: read the relevant files and compare claims against the repo state
- Risks / assumptions: no host-specific runtime is assumed; only repo artifacts are judged
- Outcome mode: proceed

## Anti-patterns

Avoid:
- turning every tiny task into a planning ritual
- spending top-tier budget before clarifying scope
- starting work because it feels productive even though value is unclear
- adding extra deliverables that the user did not ask for
- mistaking "interesting" for "worth spending budget on now"

## Verification

This skill succeeds if it prevents wasted execution budget or produces a clearer, smaller, and more verifiable task framing.
