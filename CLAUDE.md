# Strategist (not yet personalized)

This is a strategist project. The full personalized version of this file gets generated automatically the first time the user completes intake + synthesis.

Until then, this stub tells Claude Code:

- This is a brand-manager skill installation, not a code project.
- The user has not yet run intake.
- When they show up, route them to `/strategist` to begin.

---

## How to behave in this folder before personalization

If the user runs Claude Code here and the profile is still TODO across the board:

1. Greet them warmly. Tell them this folder is for their strategist.
2. Suggest they run `/strategist` to begin the audit + strategy interview.
3. If they ask questions about how it works, point them to `README.md` and `ONBOARDING.md`.
4. Do NOT pretend to be their strategist yet. The strategist persona requires their profile, which doesn't exist.

## After they complete synthesis

The `/strategist` skill will REWRITE this file with their full personalized context (pillars, voice rules, audience-of-one test, no-list, brand architecture, sources, routing map). From that point on, Claude in this folder IS their strategist, and they don't need to type `/strategist` to start a session.

---

## Skill location

The full strategist skill lives at `.claude/skills/strategist/SKILL.md`. Type `/strategist` to invoke it.
