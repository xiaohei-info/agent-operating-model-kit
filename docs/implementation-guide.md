# Implementation Guide

This document explains how to land the operating model in an existing agent environment **without** shipping host-framework entry files.

## Core Rule

This repository tells operators and agents **what to add where**.

It does **not** ship ready-to-overwrite host files like:
- `AGENTS.md`
- `SOUL.md`
- `CLAUDE.md`
- framework-specific system prompt files

Different agent stacks may already have mature versions of those files. The safe approach is to guide placement, not replace local entry points.

## What to add where

### 1. Runtime profile / system prompt layer
Put only compact, high-frequency principles here, for example:
- customer value first
- token is budget
- no concrete output means not finished
- work that cannot prove value should not consume budget
- proactively close gaps, but do not proactively expand scope

Do **not** put:
- the full doctrine
- KPI definitions
- long adoption instructions
- recurring review prompts

### 2. Governance skills
Use skills for repeatable judgment workflows such as:
- whether work should start
- what proves completion
- whether the result should become an asset

This repository includes three governance skills:
- `operating-gates`
- `delivery-review-gates`
- `assetization-closeout`

These should sit above execution skills rather than replacing them.

### 3. Recurring reviews
Use your framework’s cron or scheduler layer for periodic governance.

Recommended cadence:
- weekly operating review
- monthly doctrine audit

The goal is to inspect:
- customer value output
- token efficiency
- cycle time
- assetization rate

### 4. Memory
Use memory only for stable facts such as:
- the core customer identity
- durable environment constraints
- long-lived user preferences

Do **not** put the doctrine or long workflows into memory.

### 5. Task state
Use your framework’s task board, todo system, or plan files for:
- current work
- blockers
- next actions
- verification targets

Task state should track active execution, not permanent governance.

## Recommended rollout order

1. read the README / doctrine
2. inject a compact runtime principle excerpt
3. adopt governance skills
4. add weekly / monthly reviews
5. add framework-specific integration only where needed

## Success criteria

A successful adoption should result in:
- fewer low-value tasks being started
- more evidence-based completion claims
- more repeated work turning into reusable assets
- better budget awareness without destroying execution speed

## Non-goals

This repository is not trying to:
- define a universal agent personality
- mandate a multi-agent topology
- replace an existing execution framework
- force a single file structure on every host environment
