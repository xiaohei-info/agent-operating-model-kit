# Governance Skills

This directory contains three governance skills designed to layer on top of an existing execution stack.

## Purpose

These skills enforce decision gates and completion standards. They do not replace planning, coding, debugging, or verification workflows that the host framework already provides.

## Skills

| Skill | Trigger | Purpose |
|---|---|---|
| `operating-gates` | Before starting non-trivial work | Confirm value alignment, budget justification, scope boundaries, and whether the task should proceed |
| `delivery-review-gates` | Before claiming completion | Verify evidence, confirm scope, classify review needs, and enforce clear closeout statements |
| `assetization-closeout` | After successful or repeated work | Decide whether the result should become a reusable asset and which carrier is correct |

## Deployment pattern

These skills are designed to:
- load on demand when the trigger condition matches
- run as governance checks, not as execution drivers
- compose with host-native planning and execution flows

They should not:
- replace host-native task orchestration
- introduce new execution loops
- duplicate logic that the host framework already handles well

## Generic install guidance

1. Read each `SKILL.md` to understand trigger conditions, outcome modes, and output schemas.
2. Decide where the host framework expects governance skills to live.
3. Copy or symlink the skill directories into the host skill location.
4. Confirm the host framework loads them at the right trigger points.
5. Adjust any paths or tool references if the host stack differs.

For framework-specific mapping, see [`docs/integrations/hermes.md`](../docs/integrations/hermes.md) as a reference edge integration.

## Manual fallback when no skill loader exists

If the host cannot install reusable skills:
- use `operating-gates` as a pre-execution checklist before non-trivial work
- use `delivery-review-gates` as the closeout checklist before claiming done
- use `assetization-closeout` after repeated or high-value work

This is still a valid adoption. The key is using the governance logic at the right moment, not forcing a specific packaging mechanism.

## Trigger verification

After installation, verify the host can reliably do all three:
- before non-trivial work, produce value / deliverable / verification framing
- before closeout, produce evidence-backed completion statements
- after repeated work, decide whether to capture a reusable asset

If the host cannot do these on demand, the skills were not landed correctly even if the files were copied.

## Layer separation

- Governance logic lives here
- Runtime principles live in `SOUL.md`
- Full doctrine lives in `docs/operating-doctrine.md`
- Memory boundaries live in `MEMORY.md`
- Recurring reviews live in `templates/cron/`

Do not mirror skill content into memory or runtime layers.