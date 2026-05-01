# Governance Skills

This directory contains three governance skills designed to layer on top of an existing execution stack.

## Purpose

These skills enforce decision gates and completion standards. They do not replace planning, coding, debugging, or verification workflows that the host framework already provides.

## Skills

| Skill | Trigger | Purpose |
|---|---|---|
| `operating-gates` | Before starting nontrivial work | Confirm value alignment, token cost justification, and whether the task should proceed |
| `delivery-review-gates` | Before claiming completion | Verify evidence, confirm scope, and enforce clear closure statements |
| `assetization-closeout` | After successful delivery | Decide whether the result should become a reusable asset |

## Deployment pattern

These skills are designed to:
- load on demand when the trigger condition matches
- run as governance checks, not as execution drivers
- compose with host-native planning and execution flows

They should not:
- replace host-native task orchestration
- introduce new execution loops
- duplicate logic that the host framework already handles

## Generic install guidance

1. Read each `SKILL.md` to understand trigger conditions and steps
2. Decide where the host framework expects governance skills to live
3. Copy or symlink the skill directories into the host skill location
4. Confirm the host framework loads them at the right trigger points
5. Adjust any paths or tool references if the host stack differs

For framework-specific mapping, see `docs/integrations/hermes.md` as a reference edge integration.

## Layer separation

- Governance logic lives here
- Runtime principles live in `SOUL.md`
- Full doctrine lives in `docs/operating-doctrine.md`
- Memory boundaries live in `MEMORY.md`
- Recurring reviews live in `templates/cron/`

Do not mirror skill content into memory or runtime layers.