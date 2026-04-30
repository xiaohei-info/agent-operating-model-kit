# Example Agent Handoff

Use this when you want to give the repository to another agent and let that agent perform the rollout.

## Minimal Handoff Prompt

> Read `README.md` first. Then read `docs/operating-doctrine.md`, `docs/layering.md`, `docs/adoption-playbook.md`, and `docs/what-goes-where.md`. Adopt this operating model in the current environment. Decide what belongs in runtime principles, skills, cron, memory, docs, and task state. Start at the lowest maturity level that makes sense. Reuse the existing execution stack wherever possible. Do not rebuild planning, coding, research, or debugging workflows unless there is a clear governance gap.

## Stronger Handoff Prompt

> Your job is to implement the Agent Operating Model Kit in this environment.
>
> 1. Read `README.md` for the high-level model.
> 2. Read `docs/operating-doctrine.md` for mission, north star, iron laws, and leadership principles.
> 3. Read `docs/layering.md` and `docs/what-goes-where.md` to map doctrine into the right carriers.
> 4. Read `docs/adoption-playbook.md` to choose an appropriate maturity level.
> 5. Reuse the framework's current execution substrate where it already works well.
> 6. Implement only the smallest useful adoption layer first.
> 7. Report back with:
>    - chosen maturity level
>    - what goes into runtime principles
>    - what governance skills are needed
>    - what cron reviews should be configured
>    - what remains intentionally unchanged

## Expected Good Outcome

A good agent rollout should:
- keep the doctrine outside the live prompt except for a compact runtime excerpt
- avoid duplicating execution capabilities the framework already has
- add governance gates before adding complexity
- make adoption reviewable and reversible

## Bad Outcome

A bad agent rollout will:
- stuff the whole doctrine into runtime prompt or memory
- create a giant mega-skill
- rebuild an entire execution stack for no reason
- add cron jobs before the doctrine and gates are even stable
