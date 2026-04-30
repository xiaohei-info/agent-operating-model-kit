# Hermes Reference Integration

This file is a **reference edge integration**, not the core of the kit.

## Principle

Use the operating model as a governance overlay on top of Hermes.

Do not replace Hermes' existing execution substrate if it already works well.

## Suggested Hermes Mapping

### Runtime layer
Inject only a compact set of runtime principles into the Hermes profile / prompt layer.

Examples:
- customer value first
- token is budget
- no concrete output means not finished
- work that cannot prove value should not consume budget

### Skills layer
Adopt the governance skills from this repository:
- `operating-gates`
- `delivery-review-gates`
- `assetization-closeout`

Keep using Hermes' own execution skills for planning, coding, research, debugging, and verification.

### Review cadence
Use Hermes `cronjob` or the equivalent scheduler to run:
- a weekly operating review
- a monthly doctrine audit

### Memory layer
Use Hermes `memory` for stable customer and environment facts only.

### Task state
Use Hermes `todo` or plan files for active execution state.

## What Not to Do

Do not:
- copy this repository into `~/.hermes` wholesale
- replace Hermes profile files blindly
- turn the governance skills into broad execution skills
- duplicate Hermes execution workflows if the existing ones are already sufficient

## Success Condition

A good Hermes adoption should:
- improve budget discipline
- improve completion quality
- improve assetization
- preserve the strengths of Hermes' existing execution stack
