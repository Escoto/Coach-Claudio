# Coach Claudio

A training coach powered by Claude Code. Works for triathletes, runners, cyclists, bodybuilders, and any endurance or strength athlete. Provides weekly planning, session review, and training analysis — driven by your data.

## Quick Start

1. Clone this repo
2. Open the directory in [Claude Code](https://claude.ai/code)
3. Run `/onboard` to set up your athlete profile
4. Start coaching:
   - `/plan-week` — generate your next training week
   - `/review-session` — analyze a recent workout
   - `/review-week` — summarize your past week

## Skills

| Command | What it does |
|---------|-------------|
| `/onboard` | Conversational intake to build your athlete profile (goals, availability, fitness, injuries). Run this first. See [[onboard]]. |
| `/plan-week` | Generates a Monday-Sunday training plan with [[readiness gates\|readiness gates]], [[intensity-zones\|intensity targets]], and [[periodization\|progression guardrails]]. See [[plan-week]]. |
| `/review-session` | Deep analysis of a single training session — plan vs execution, [[intensity-zones\|intensity zones]], coaching observations. See [[review-session]]. |
| `/review-week` | Full weekly summary — volume, [[recovery-monitoring\|recovery trends]], execution vs plan, flags, and a primer for next week. See [[review-week]]. |

## Data Sources

Coach Claudio works with whatever data you have:

### Option 1: MCP Server (automatic)
If you have a fitness MCP server registered (Garmin, Strava, etc.), the coach detects it automatically and pulls data directly. No CSV needed.

To register a Garmin MCP server:
```bash
claude mcp add garmin -e GARMIN_EMAIL="you@email.com" -e GARMIN_PASSWORD="yourpass" -- node /path/to/garmin-connect-mcp/build/index.js
```

### Option 2: CSV Files
Export your training data as CSV and place it in the repo. See [[csv-import-guide]] for the format spec and export instructions for Garmin, Strava, and Apple Health.

### Option 3: Manual
Describe your sessions in plain text. The coach works with whatever you give it.

## Directory Structure

```
Coach-Claudio/
  CLAUDE.md              # Coaching persona and operational instructions
  coach-knowledge/       # Training science knowledge base (Obsidian-compatible)
    _index.md            # Map of Content
    thresholds.md        # All hard numerical guardrails
    periodization.md     # Mesocycles, progression, session sequencing
    recovery-monitoring.md # HRV, readiness, sleep, ACWR, deload triggers
    intensity-zones.md   # Zone models, RPE scales, polarized distribution
    sport-adaptations.md # Endurance, strength, hybrid guidance
    injury-prevention.md # Load management, red/yellow flags
    nutrition.md         # Fueling, event nutrition, weight management
  .claude/
    skills/              # The 4 coaching skills
    memory/              # Your athlete profile (gitignored)
  templates/             # Output format references and CSV guide
  athlete_plan/          # Generated plans and logs (gitignored)
```

Your personal data (athlete profile, training plans, weekly logs) is gitignored by default. If you fork this repo and push to your own GitHub, your training stays private.

## Knowledge Base

The `coach-knowledge/` directory contains training science, recovery protocols, and sport-specific guidance as individual Markdown files with Obsidian-compatible linking. Open the [[_index|Map of Content]] for a map of all topics. You can browse and extend this knowledge base using [Obsidian](https://obsidian.md) if desired.

| Knowledge File | Covers |
|---------------|--------|
| [[thresholds]] | All hard numerical guardrails (single source of truth) |
| [[periodization]] | Mesocycles, progression, session sequencing, readiness gates |
| [[recovery-monitoring]] | HRV, readiness, sleep, ACWR, deload triggers |
| [[intensity-zones]] | Zone models, RPE scales, cardiac drift, recovery estimation |
| [[sport-adaptations]] | Endurance, strength, hybrid athlete guidance |
| [[injury-prevention]] | Load management, red/yellow flags |
| [[nutrition]] | Fueling, event nutrition, weight management |

## Customization

- **Athlete profile:** Run [[onboard|/onboard]] again to update any section
- **MCP servers:** Add your fitness platform MCP in `.claude/settings.local.json`
- **Model:** Set your preferred Claude model in `.claude/settings.json`

## License

This project is licensed under the [GNU General Public License v3.0](LICENSE).

## Version

v0.0.1
