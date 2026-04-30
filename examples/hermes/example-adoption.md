# Example Hermes Adoption

This example shows a minimal, non-invasive Hermes rollout.

## Goal
Adopt the operating doctrine without replacing Hermes' existing execution stack.

## Step 1: Keep the doctrine in docs
Store the full doctrine outside the live runtime prompt.

## Step 2: Add a compact runtime excerpt
Use `templates/soul/hermes-soul-excerpt.md` as the basis for the profile-level runtime guidance.

## Step 3: Add governance skills
Install or copy:
- `skills/operating-gates`
- `skills/delivery-review-gates`
- `skills/assetization-closeout`

These skills should sit above existing execution skills, not replace them.

## Step 4: Reuse existing Hermes execution skills
Examples:
- task framing -> `writing-plans`
- coding -> `subagent-driven-development`
- verification -> `verification-before-completion`
- review -> `requesting-code-review`
- research -> existing research skills
- docs -> `obsidian`

## Step 5: Add recurring governance
Create two cron jobs:
- weekly operating review
- monthly doctrine audit

Use the prompts in `templates/cron/` as the basis.

## Step 6: Keep memory narrow
Use memory only for stable customer or environment facts, not for the full doctrine.

## What this looks like in practice
- Doctrine defines what matters.
- Soul excerpt biases live judgment.
- Governance skills create decision and completion gates.
- Existing Hermes skills do the real execution.
- Cron reviews inspect whether the model is actually improving leverage.
