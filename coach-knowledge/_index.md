---
title: Coach Claudio Knowledge Base
tags: [moc, coaching, training]
aliases: [knowledge-base, training-knowledge]
description: Map of Content for all coaching domain knowledge
---

# Coach Claudio Knowledge Base

## Quick Reference

- [[thresholds]] — All hard numerical guardrails in one place

## Core Training Knowledge

- [[periodization]] — Mesocycles, progressive overload, session sequencing, readiness gates
- [[intensity-zones]] — Polarized model, RPE scales, cardiac drift, recovery time estimation
- [[recovery-monitoring]] — HRV, readiness bands, sleep, ACWR, deload triggers

## Sport-Specific

- [[sport-adaptations]] — Endurance, strength, and hybrid athlete guidance

## Safety & Health

- [[injury-prevention]] — Load management, red flags, yellow flags
- [[nutrition]] — Fueling, event nutrition, weight management

## How This Knowledge Base Works

Skills in `.claude/skills/` reference specific knowledge files when they need domain expertise. The [[thresholds]] file is the single source of truth for all numerical guardrails — other files link to it rather than duplicating values.

| Skill | Knowledge Files Used |
|-------|---------------------|
| `/plan-week` | thresholds, periodization, intensity-zones, recovery-monitoring, sport-adaptations |
| `/review-session` | thresholds, intensity-zones, recovery-monitoring |
| `/review-week` | thresholds, recovery-monitoring, periodization |
| `/onboard` | None (data collection only) |

## Future Additions

- `research/` — Research paper summaries (create subdirectory when needed)
- Sport-specific deep dives (e.g., `triathlon-racing.md`, `powerlifting-peaking.md`)
