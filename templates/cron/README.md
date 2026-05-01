# Recurring Governance Templates

This directory contains periodic review prompts designed to run on a scheduler.

## Purpose

These templates enforce recurring governance: weekly KPI review and monthly doctrine audit. They detect drift and keep the operating model aligned over time.

## Templates

| Template | Default cadence | Purpose |
|---|---|---|
| `weekly-operating-review.md` | Weekly | Inspect value creation, spend efficiency, assetization rate, and operating drift |
| `monthly-operating-audit.md` | Monthly | Compare installed surfaces against the canonical charter, detect drift, and propose calibration |

## Deployment pattern

These templates are designed to:
- run on a host scheduler (cron, systemd timer, framework job system)
- inspect the current state and report findings
- propose adjustments but not auto-execute them

They should not:
- introduce new background processes without scheduler integration
- run inline inside active task sessions
- generate assets or modify files autonomously without explicit approval

## Generic install guidance

1. Choose a cadence for each template (weekly/monthly are defaults).
2. Decide what scheduler the host environment uses.
3. Wire the prompt as a scheduled job with appropriate delivery target.
4. Confirm the job runs in a fresh session with access to the relevant layers.
5. Adjust inputs/outputs if the host stack differs.

For framework-specific mapping, see [`docs/integrations/hermes.md`](../../docs/integrations/hermes.md) as a reference edge integration.

## Manual fallback when no scheduler exists

If the host has no scheduler:
- keep the same prompts
- run the weekly review manually on a weekly rhythm
- run the monthly doctrine audit manually on a monthly rhythm
- treat them as recurring governance rituals rather than background automation

Lack of scheduling should reduce automation, not remove review discipline entirely.

## Minimum evidence inputs

Both templates work best when they can inspect:
- `docs/operating-doctrine.md` for charter comparison
- `SOUL.md` for runtime principle comparison
- recent task logs, session summaries, or work history
- recently created skills/docs/templates when assetization is being judged

## Output target

Both templates should produce:
- a short summary of current state vs intended model
- a list of detected drifts or gaps
- proposed adjustments with rationale
- clear routing for those adjustments

Typical routing:
- doctrine clarification → `docs/operating-doctrine.md`
- runtime compression change → `SOUL.md`
- reusable gate logic change → `skills/`
- recurring review improvement → `templates/cron/`
- local environment fact → memory or local notes

Delivery should go to a channel the operator reads regularly.

## Review quality check

Recurring review is healthy when it:
- identifies actual waste or drift
- recommends a small number of concrete changes
- improves future work rather than expanding ceremony

Recurring review has drifted into theater when it:
- produces long summaries with no action
- repeats the same findings without structural change
- expands governance overhead faster than it improves outcomes

## Layer separation

- Recurring prompts live here
- Governance logic lives in `skills/`
- Runtime principles live in `SOUL.md`
- Full doctrine lives in `docs/operating-doctrine.md`
- Memory boundaries live in `MEMORY.md`

Do not mirror review prompts into memory or runtime layers.