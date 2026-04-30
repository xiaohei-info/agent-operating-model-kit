# Layering Model

This repository is designed as a **governance overlay**, not as a replacement execution stack.

The central design principle is:

**Do not mix doctrine, runtime bias, execution mechanics, review cadence, and persistent facts in one container.**

## Layer 0: Doctrine

### Purpose
Defines what the organization is, why it exists, what it optimizes for, and what it refuses to do.

### Typical contents
- customer definition
- mission
- existential purpose
- north star
- leadership principles
- iron laws
- company-level KPI definitions

### Best carrier
- long-form docs

### Not for
- per-turn prompt stuffing
- task state
- volatile implementation details

---

## Layer 1: Runtime Principles

### Purpose
Translate doctrine into a compact set of high-frequency judgment biases that can safely influence live execution.

### Typical contents
- customer value first
- token is budget
- no output means not finished
- prefer assetization over repeated one-off effort
- proactive gap-closing, not proactive scope expansion

### Best carrier
- runtime profile excerpt
- profile charter
- compact system prompt overlay
- framework-specific soul layer if that is the local term

### Not for
- KPI tables
- long explanations
- framework-specific how-to steps

---

## Layer 2: Operating Gates

### Purpose
Turn abstract principles into concrete decision gates that can be applied before starting work, before claiming completion, and when deciding whether to assetize.

### Typical contents
- value gate
- budget gate
- completion gate
- verification/review gate
- assetization gate

### Best carrier
- small governance skills
- checklists
- review rubrics

### Not for
- being the main execution engine
- replacing the framework's own implementation skills

---

## Layer 3: Execution Substrate

### Purpose
The actual doing layer: planning, coding, research, debugging, tool use, delegation, review execution.

### Typical contents
- planning skills
- coding skills
- debugging skills
- review skills
- docs and note-taking skills
- subagent and parallel work systems

### Best carrier
- the host agent framework and its existing skills

### Note
This repository intentionally assumes this layer already exists and should mostly be reused rather than rebuilt.

---

## Layer 4: Task State

### Purpose
Track active work and short-horizon execution state.

### Typical contents
- current tasks
- status transitions
- next actions
- blockers
- verification target

### Best carrier
- task board
- todo tool
- plan files
- lightweight task schema

### Warning
Do not prematurely build a heavy task operating system if the host framework already has sufficient active-task tracking.

---

## Layer 5: Review Cadence and KPIs

### Purpose
Create recurring governance so the system can be evaluated and adjusted.

### Typical contents
- weekly operating review
- monthly doctrine audit
- KPI review prompts
- drift detection questions

### Best carrier
- cron jobs
- recurring review templates
- periodic docs

---

## Layer 6: Asset Layer

### Purpose
Capture reusable residue from work so future budget goes further.

### Typical contents
- skills
- scripts
- SOPs
- docs
- templates
- cron jobs
- decision notes

### Best carrier
- version-controlled files
- framework-native skill systems
- knowledge bases

---

## Mapping Guidance

### Put it in docs when
- humans need to understand or debate it
- it is long-lived doctrine or rationale

### Put it in a runtime profile or prompt layer when
- it should influence nearly every live decision
- it can be compressed to a few stable lines

### Put it in a skill when
- it has trigger conditions and repeatable steps
- it improves judgment through a reusable procedure

### Put it in cron when
- it is periodic governance, not task-local behavior

### Put it in memory when
- it is a stable fact about the customer, environment, or recurring preference

### Put it in task state when
- it is about current execution, not long-term rules

## Anti-Patterns

Avoid:
- putting the full doctrine into memory
- stuffing KPI definitions into soul
- turning governance skills into replacement execution skills
- creating a new task system before proving the existing one is insufficient
- writing assets that duplicate existing framework capabilities without leverage
