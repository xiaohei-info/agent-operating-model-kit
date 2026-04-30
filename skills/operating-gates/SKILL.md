---
name: operating-gates
description: Use before starting non-trivial work to decide whether the task should consume budget now, what success looks like, and whether a lighter path exists.
version: 0.1.0
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

## The Gates

### 1. Value Gate
Answer:
- What customer value will this produce?
- Why is it worth doing now?
- What concrete output would make it successful?

If you cannot answer these, do not expand into execution yet.

### 2. Budget Gate
Answer:
- Does this require heavy reasoning, multiple agents, or many tools?
- Is that spend justified by expected value?
- Is there a lighter path that would preserve correctness?

Prefer the lowest-cost path that still achieves a verified result.

### 3. Scope Gate
Answer:
- What is in scope?
- What is explicitly out of scope?
- What assumptions are being made?

State assumptions rather than silently expanding the task.

### 4. Output Gate
Define before starting:
- deliverables
- verification method
- important risks or side effects

If there is no concrete output or no verification method, the task is not ready for heavier execution.

## Minimal Output Pattern

For non-trivial tasks, produce a compact framing before execution:
- Goal
- Deliverables
- Verification
- Risks / assumptions

## Anti-Patterns

Avoid:
- turning every tiny task into a planning ritual
- spending top-tier budget before clarifying scope
- starting work because it feels productive even though value is unclear
- adding extra deliverables that the user did not ask for

## Verification

This skill succeeds if it prevents wasted execution budget or produces a clearer, smaller, and more verifiable task framing.
