# Recurring Governance Templates

This directory contains periodic review prompts designed to run on a scheduler.

## Purpose

These templates enforce recurring governance: weekly KPI review and monthly doctrine audit. They detect drift and keep the operating model aligned over time.

## Templates

| Template | Default cadence | Purpose |
|---|---|---|
| `weekly-operating-review.md` | Weekly | Inspect value creation, token efficiency, assetization rate, and operating drift |
| `monthly-operating-audit.md` | Monthly | Compare installed layers against the canonical charter, detect drift, propose calibration |

## Deployment pattern

These templates are designed to:
- run on a host scheduler (cron, systemd timer, framework job system)
- inspect the current state and report findings
- propose adjustments but not auto-execute them

They should not:
- introduce new background processes without scheduler integration
- run inline inside active task sessions
- generate assets or modify files autonomously

## Generic install guidance

1. Choose a cadence for each template (weekly/monthly are defaults)
2. Decide what scheduler the host environment uses
3. Wire the prompt as a scheduled job with appropriate delivery target
4. Confirm the job runs in a fresh session with access to the relevant layers
5. Adjust inputs/outputs if the host stack differs

For framework-specific mapping, see `docs/integrations/hermes.md` as a reference edge integration.

## Required inputs

Both templates expect:
- access to `docs/operating-doctrine.md` for charter comparison
- access to `SOUL.md` for runtime principle comparison
- access to recent session logs or work history for drift detection

## Output target

Both templates produce:
- a summary of current state vs intended model
- a list of detected drifts or gaps
- proposed adjustments with rationale

Delivery should go to a channel the operator reads regularly.

## Layer separation

- Recurring prompts live here
- Governance logic lives in `skills/`
- Runtime principles live in `SOUL.md`
- Full doctrine lives in `docs/operating-doctrine.md`
- Memory boundaries live in `MEMORY.md`

Do not mirror review prompts into memory or runtime layers.