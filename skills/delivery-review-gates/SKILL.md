---
name: delivery-review-gates
description: Use before claiming work is complete to enforce output clarity, verification evidence, review expectations, and side-effect awareness.
version: 0.2.0
author: Agent Operating Doctrine
license: MIT
---

# Delivery Review Gates

## Overview

This skill governs the end of a task. It is for checking whether work is truly ready to report as complete.

## Use This When

Use when:
- you are about to say a task is done
- you are wrapping up code, research, or configuration work
- delegated or multi-step work has returned and needs final validation
- the result has side effects or could be mistaken as finished when it is not

## The gates

### 1. Deliverable gate
Ask:
- What exactly is the output?
- Is it concrete enough for the customer to inspect or use?

If the output is vague, the task is not ready to close.

### 2. Verification gate
Ask:
- What fresh evidence proves the claim?
- What command, file check, or reproduction path supports completion?

No completion claims without fresh evidence.

### 3. Review gate
Ask:
- Does this require a second perspective?
- Is the risk level high enough that independent review is warranted?

For low-risk work, explicit self-verification may be enough. For higher-risk work, require an independent check or human confirmation.

### 4. Side-effect gate
Ask:
- Did this modify configuration, data, services, or external state?
- Was the side-effect within authorized scope?
- Does the customer need to confirm anything before proceeding further?

### 5. Boundary gate
Ask:
- What remains unverified?
- What limits or known issues should be disclosed?

Never report full completion when material uncertainty remains.

## Risk classes

### Low risk
Typical examples:
- docs-only changes
- low-impact summaries
- reversible wording or formatting edits

Usually enough:
- self-verification
- explicit disclosure of limits if any remain

### Medium risk
Typical examples:
- meaningful code or config changes in a non-critical environment
- research that will shape a decision
- changes with moderate downstream effect but good reversibility

Usually enough:
- fresh verification evidence
- second perspective when feasible
- clear disclosure of assumptions and unverified edges

### High risk
Typical examples:
- destructive changes
- production or security-sensitive changes
- external actions with financial, legal, or reputational consequence
- any irreversible step the customer would reasonably expect to approve personally

Usually required:
- strong verification evidence
- independent review or human confirmation
- explicit disclosure of remaining risks before final action

## Evidence examples by task type

### Documentation / repo structure
- read the changed file
- inspect the diff
- verify links/paths exist if claimed

### Code or config change
- run the relevant test, build, or validation command
- inspect affected files directly
- reproduce the original failure path when applicable

### Research or evaluation
- cite the sources actually used
- separate fact from interpretation
- state what remains uncertain

### Operational change
- show the exact command or observable signal proving the effect
- disclose any irreversible or externally visible side effect

## Closeout outcome modes

Before reporting up, decide which of these is true:
- **Complete** — deliverable is concrete and evidence supports the claim
- **Complete with limits** — usable output exists, but meaningful boundaries remain and are disclosed
- **Needs review** — output may be correct, but risk or uncertainty is high enough that another perspective should inspect it first
- **Not ready to close** — output, evidence, or scope clarity is insufficient

## Recommended closeout format

Use the structure from [`templates/review/task-closeout-template.md`](../../templates/review/task-closeout-template.md):
- What I changed or produced
- How I verified it
- Known limits or unverified edges
- Suggested next step

## Strong closeout behavior

Good:
- claim only what the evidence supports
- say what remains limited or unverified
- separate factual completion from recommended next steps

Bad:
- reporting vibes instead of evidence
- presenting partial verification as full verification
- hiding assumptions or known gaps to make the output seem more finished
- treating review as optional for risky work

## Verification

This skill succeeds if completion claims become more evidence-based, lower-risk, and easier to trust.
