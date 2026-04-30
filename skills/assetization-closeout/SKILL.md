---
name: assetization-closeout
description: Use after valuable or repeated work to decide whether the result should become a reusable asset such as a skill, doc, SOP, script, template, or cron workflow.
version: 0.1.0
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

## The Questions

### 1. Repetition Test
Will this problem or workflow likely happen again?

### 2. Leverage Test
Would capturing this once reduce future token, time, or error cost?

### 3. Carrier Test
What is the right asset type?
- skill
- document
- SOP
- script
- template
- cron job
- memory fact

### 4. Scope Test
Does the asset need to be generic, or is it specific to one project or environment?

### 5. Maintenance Test
Will this asset remain useful enough to justify maintaining it?

## Asset Selection Heuristics

Use:
- a **skill** for reusable judgment + workflow
- a **doc/SOP** for human-readable explanation or governance
- a **script** for stable mechanical repetition
- a **template** for repeatable structure
- **memory** for compact stable facts, not procedures
- **cron** for recurring autonomous review or collection

## Minimal Closeout Output

When assetization is justified, state:
- what should be captured
- in what form
- why that form is the right one

## Anti-Patterns

Avoid:
- writing assets for every task
- storing one-off project residue as a reusable skill
- putting long procedures into memory
- creating documents nobody will consult again

## Verification

This skill succeeds if it increases reuse without creating clutter.
