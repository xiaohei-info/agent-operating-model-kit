# Hermes Integration Guide

This document explains how to adopt the operating model in Hermes without fighting Hermes' existing strengths.

## Guiding Rule

Use this model as a **governance overlay** on top of Hermes.

Do not treat it as a replacement for:
- Hermes tool use
- Hermes skill ecosystem
- Hermes delegation model
- Hermes todo/task tracking
- Hermes cron support

## What Goes Where in Hermes

### Doctrine
Put long-form doctrine in version-controlled docs or in a knowledge base note. Do not inject the full doctrine into the live prompt.

### Runtime Principles
Put the compact excerpt in:
- a profile charter
- a constrained soul layer
- or a system prompt overlay

### Operating Gates
Use small governance skills to decide:
- whether to start work
- whether completion is real
- whether the result should become an asset

### Execution
Reuse Hermes' existing execution skills, for example:
- `brainstorming`
- `writing-plans`
- `subagent-driven-development`
- `verification-before-completion`
- `requesting-code-review`
- `systematic-debugging`
- `obsidian`

### Task State
Use Hermes `todo` for active work unless you have proven you need a more persistent task board.

### KPI Review
Use Hermes `cronjob` for:
- weekly operating review
- monthly doctrine audit

### Durable Facts
Use Hermes `memory` for stable customer and environment facts only. Do not store the full doctrine or KPI framework in memory.

## Suggested Hermes Mapping

### Soul / Profile Excerpt
Use the file under `templates/soul/hermes-soul-excerpt.md` as the starting point, not the full doctrine.

### Governance Skills
Install or copy these skills into Hermes if useful:
- `operating-gates`
- `delivery-review-gates`
- `assetization-closeout`

### Weekly Review Cron
Create a weekly cron that answers:
- what value was created
- where token spend was wasteful
- what slowed cycle time
- what was or was not assetized

### Monthly Audit Cron
Create a monthly cron that answers:
- where the system drifted from doctrine
- which principles were repeatedly violated
- what should become a new rule, skill patch, or template update

## What Not to Port Blindly

Do not blindly port:
- another framework's role taxonomy
- local file paths
- hard-coded task-state file structures
- old execution workflows that Hermes already has a better equivalent for

## Recommended First Hermes Rollout

1. keep doctrine in docs
2. add the runtime excerpt to the target profile
3. adopt the governance skills
4. add weekly and monthly review cron jobs
5. only then decide whether more structural packaging is needed

## Why This Works

Hermes already has strong execution primitives. The missing layer in many deployments is not execution, but governance:
- when to spend budget
- what counts as complete
- what must be reviewed
- what should become an asset
- how to measure drift over time

This operating model is designed to fill that governance gap.
