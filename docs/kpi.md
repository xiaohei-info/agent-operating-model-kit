# Company-Level KPI Framework

This document defines **organization-level KPIs** for a single-customer micro AI organization. These metrics are intentionally lightweight. They are meant to improve judgment and review, not to create fake precision.

## The Four Core KPIs

### 1. Customer Value Output

**Question:** What meaningful customer value was actually created?

Examples of evidence:
- an adopted decision memo
- a working fix or implementation
- a verified research deliverable used for action
- a process improvement that reduced customer effort or risk
- a reusable asset that will save future budget

#### Review prompts
- Which outputs were actually used?
- Which outputs reduced time, errors, or uncertainty?
- Which outputs only looked polished but had little downstream effect?

---

### 2. Token Efficiency

**Question:** How much useful value did the organization create per unit of expensive reasoning and execution cost?

This is not just a cost minimization metric. Cheap but wrong work is not efficient.

#### Signs of poor token efficiency
- over-researching trivial tasks
- too many agents for a small problem
- long answers where short actionable outputs would suffice
- repeated one-off work that should have become an asset
- expensive top-model usage without a leverage point

#### Review prompts
- Which tasks were over-engineered?
- Which tasks used more reasoning than the value justified?
- Where could a lighter path have produced the same accepted outcome?

---

### 3. Cycle Time

**Question:** How long does it take to turn a need into a verified deliverable?

Cycle time matters because slow systems burn attention and lose context.

#### Things to look for
- where tasks stalled
- whether delays were caused by missing specs, weak verification, or unclear ownership
- whether a task bounced between analysis and execution without converging

#### Review prompts
- Which tasks moved smoothly?
- Which tasks dragged, and at what stage?
- What structural change would shorten similar future tasks?

---

### 4. Assetization Rate

**Question:** How much work became reusable structure rather than disappearing after one run?

Examples of assets:
- skills
- scripts
- SOPs
- templates
- cron jobs
- docs
- reusable configs
- operating rules

#### Review prompts
- Which tasks produced reusable assets?
- Which repetitive tasks remained one-off?
- Which lessons should have been captured but were lost?

---

## Suggested Lightweight Scorecard

Use a simple 0-3 score per KPI in reviews.

### Customer Value Output
- 0 = low or unclear value
- 1 = some useful output, low impact
- 2 = clearly useful output adopted or acted on
- 3 = high-leverage output with durable downstream value

### Token Efficiency
- 0 = visibly wasteful
- 1 = acceptable but inefficient
- 2 = efficient for value delivered
- 3 = unusually high leverage per unit cost

### Cycle Time
- 0 = stalled or bloated
- 1 = slow with avoidable friction
- 2 = reasonable end-to-end speed
- 3 = fast without sacrificing quality

### Assetization Rate
- 0 = no durable residue
- 1 = some partial residue
- 2 = at least one clearly reusable asset
- 3 = strong compounding structure created

## What Not to Do

Do not turn this into vanity math.

Avoid:
- fake token accounting without decision value
- role-level micro-scoring too early
- counting documents as assets when nobody will reuse them
- praising speed when it degraded correctness

## Recommendation

Start with these company-level KPIs only. Add role- or workflow-specific KPIs later, and only if they clearly improve decision quality rather than creating reporting overhead.
