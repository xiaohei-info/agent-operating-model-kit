---
name: assetization-closeout
description: Use after valuable or repeated work to decide whether the result should become a reusable asset such as a skill, doc, SOP, script, template, or cron workflow.
version: 0.2.0
author: Agent Operating Doctrine
license: MIT
---

# Assetization Closeout

## Overview

This skill helps convert one-off work into compounding organizational assets. It should be used after meaningful tasks, especially repeated tasks or tasks that revealed a reusable workflow.

## Use This When

Use when:
- a task took multiple steps and is likely to recur
- a workflow, checklist, or pattern was discovered
- an error or recovery path should be remembered structurally
- a result could save future budget if captured once

Do not use for:
- trivial one-off outputs with no reuse value
- temporary task state
- raw session diaries

## The questions

### 1. Repetition test
Will this problem or workflow likely happen again?

### 2. Leverage test
Would capturing this once reduce future token, time, or error cost?

### 3. Carrier test
What is the right asset type?
- skill
- document
- SOP
- script
- template
- cron job
- memory fact

### 4. Scope test
Does the asset need to be generic, or is it specific to one project or environment?

### 5. Maintenance test
Will this asset remain useful enough to justify maintaining it?

## Strong assetization signals

Assetization is usually justified when one or more are true:
- the workflow or judgment has already repeated
- the same confusion or failure is likely to recur
- future operator steering would be reduced materially
- the captured asset would save meaningful time or error cost
- the pattern is stable enough to describe without hand-waving

## Weak assetization signals

Assetization is usually not justified when:
- the work is memorable but likely one-off
- the pattern is still too unstable to describe cleanly
- the asset would duplicate stronger existing structure
- the maintenance burden would exceed likely reuse
- the material is mostly raw residue rather than a reusable pattern

## Carrier decision matrix

### Use a skill when
- the value is reusable judgment plus workflow
- trigger conditions are recognizable
- the process is repeatable across tasks

### Use a doc or SOP when
- the value is durable explanation, rationale, policy, or step order
- a human or agent will benefit from reading the reasoning directly

### Use a script when
- the work is mostly stable mechanical repetition
- the logic is precise enough to automate safely

### Use a template when
- the structure repeats more than the reasoning does
- you want consistent output shape

### Use a cron job when
- the value comes from recurring execution over time
- the same review or collection should happen on a schedule

### Use memory only when
- the information is a compact stable fact
- it reduces future steering
- it is not actually a procedure, doctrine rule, or temporary state

## Generic vs local assets

Before creating an asset, decide which bucket it belongs in:

### Generic asset
Use when:
- the pattern transfers across projects or environments
- the instructions do not depend heavily on local paths or one user's setup

Typical carriers:
- open-source skill
- reusable template
- general doctrine doc

### Local asset
Use when:
- the pattern depends on one environment, repo, deployment, or operator
- the details would mislead adopters outside that context

Typical carriers:
- project SOP
- local script
- environment-specific note
- local memory fact

## Minimal closeout output

When assetization is justified, state:
- what should be captured
- in what form
- why that form is the right one
- whether it is generic or local

## "Do not assetize yet" rule

If the pattern is still changing fast, say so explicitly instead of forcing a premature asset. A living note or temporary project doc is often better than a low-quality skill created too early.

## Anti-patterns

Avoid:
- writing assets for every task
- storing one-off project residue as a reusable skill
- putting long procedures into memory
- creating documents nobody will consult again
- creating public assets from host-specific details that will not transfer

## Verification

This skill succeeds if it increases reuse without creating clutter.
