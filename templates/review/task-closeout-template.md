# Task Closeout Template

Use this structure when standardizing delivery closeout.

## Purpose

Enforce clear, evidence-based completion claims and reduce vague "done" statements.

## Recommended closeout format

When reporting work complete, include:

### What I changed or produced
- concrete output: files, configs, code, docs, scripts, templates, or decisions
- scope: what was in scope and what was explicitly out of scope
- assumptions: any assumptions that shaped the result

### How I verified it
- fresh evidence: commands run, checks passed, files inspected, diff read
- reproduction path: how another agent or human could verify the same claim
- any independent review if required

### Known limits or unverified edges
- what remains unverified
- what limits or caveats apply
- what risks or side effects should be disclosed

### Suggested next step
- what the customer or next agent should do next
- any follow-up work that remains

## Worked example: documentation change

### What I changed or produced
- rewrote `README.md` and `docs/implementation-guide.md`
- kept repository structure unchanged
- out of scope: no runtime behavior or host config changes

### How I verified it
- re-read both files after editing
- inspected `git diff` to confirm the changes matched the request
- checked that referenced file paths still exist

### Known limits or unverified edges
- no live host adoption was performed in this repo-only change
- framework-specific integrations were not re-tested beyond document consistency

### Suggested next step
- run a repo-link-only adoption dry run in a fresh session or host

## Worked example: code or config change

### What I changed or produced
- updated the target configuration file to add the requested setting
- out of scope: unrelated refactors or service redesign

### How I verified it
- ran the relevant validation command
- inspected the changed file directly
- confirmed the expected output / exit status

### Known limits or unverified edges
- change was validated in the current environment only
- production rollout not performed yet

### Suggested next step
- have the operator approve deployment or run the production-specific verification path

## Strong closeout claims

Good closeouts:
- state exactly what was produced
- show fresh verification evidence
- disclose limits honestly
- stay short and concrete

Bad closeouts:
- "I think it's done"
- "everything works now"
- "just run it"
- hiding assumptions or known gaps

## Constraints

Do not:
- report completion without concrete output
- report completion without fresh verification evidence
- hide limits or unverified edges
- expand scope after the fact without disclosure

## Success condition

This template succeeds if:
- completion claims become inspectable and reproducible
- vague "done" statements are replaced by evidence-backed closeouts
- downstream work has clear context about limits and next steps