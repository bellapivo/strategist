# strategist

A fractional brand manager + social media manager you run in your terminal. Built on Claude Code.

You install it, run `/strategist`, and it interviews you to build a profile — your audience-of-one, your pillars, your voice rules, your no-list. Then it operates against that profile: grills your ideas one open question at a time, drafts in your actual voice (never fabricated), hunts teardown targets, walks comment replies, runs weekly strategy reviews.

It's not anyone specific. **It's the strategist who would build your brand if you could afford to hire one.**

---

## Who this is for

Four rough profiles. The intake adapts based on which one you are.

- **Discovery mode** — you have real substance (work, expertise, life) but no content brain yet. You don't know what your voice is. Run the full 45-min intake; strategist proposes pillars + voice + audience from what you say.
- **Established brand** — you already have a voice, audience, and pillars *in your head*, but they're not written down anywhere. The intake captures and locks them so future sessions stop re-deriving from scratch.
- **Grassroots / no social** — you have a product (book, art, course, service) and basically no audience. You're not sure you want to be a "creator." You need a non-creator playbook.
- **Has-a-brand-manager-system** — you already have strategy docs, voice rules, audience personas, no-lists documented somewhere (a vault, Notion, content-strategy doc). Tell the strategist where to look at the start. It'll ingest, reconcile any conflicts between sources, and hand off — pillar refinement after enough new transcripts is its main ongoing value-add, not setup.

The flow (intake → always-on system → operate) is universal. The application is per-user.

---

## How it works

Three-phase architecture:

```
┌─────────────────────────────────────────────────────────────────┐
│  PHASE 1: INTAKE (~45 min) — who you are                        │
│  Bio interview, writing samples, speaking sample/voice dump,    │
│  voice north stars. Synthesis proposes pillars + voice + audience│
│  + no-list. Profile locks. CLAUDE.md is generated.              │
└─────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────┐
│  PHASE 2: BUILD YOUR ALWAYS-ON SYSTEM (~10–20 min, optional)    │
│  2 independent sub-tracks:                                      │
│  A. Meeting parser  — Granola/Otter/voice memos → inbox/        │
│  B. Trend watcher   — Reddit/RSS/HN/PH → trend-sources.md       │
│  (stats + sentiment tracking deferred — revisit after 30 days)  │
└─────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────┐
│  PHASE 3: OPERATE — continuous learning                         │
│  Every invocation: scan inbox, mine new content, update pillar  │
│  tracking. Grill seeds. Generate drafts. Hunt trends. Walk      │
│  replies. Strategy reviews. 30-day pillar refinement.           │
└─────────────────────────────────────────────────────────────────┘
```

**After Phase 1 synthesis, a `CLAUDE.md` is written to the project root.** This file is auto-loaded every time the user opens Claude Code in this folder — meaning their AI is *their* AI by default. They can say "I have an idea" without typing any slash command and Claude already knows who they are, what their pillars are, what's off-limits, and how they sound.

---

## File layout

```
strategist/
├── CLAUDE.md                       # auto-loaded by Claude Code in this folder
│                                   # (stub before setup; full personalized brain after synthesis)
├── .claude/skills/strategist/
│   └── SKILL.md                    # the whole brain — framework, verbs, flows, learning loops
├── profile/                        # YOUR data
│   ├── strategy.md                 # end goal, pillars, 90-day picture
│   ├── voice-profile.md            # voice rules, rewrites log (grows continuously)
│   ├── audience.md                 # audience-of-one + the test
│   ├── no-list.md                  # off-limits (grows from operation)
│   ├── brand-architecture.md       # one brand or split
│   ├── sources.md                  # transcript tools + inbox paths (Phase 2A)
│   ├── trend-sources.md            # subreddits, RSS, HN, PH (Phase 2B)
│   ├── pillar-tracking.md          # hit counts + emergent topics (continuous)
│   ├── audit/
│   │   ├── about-you.md            # bio interview — 6 Q
│   │   ├── written-samples.md
│   │   ├── speaking-samples.md
│   │   ├── voice-north-stars.md
│   │   └── voice-dump.md
│   ├── voice-samples/              # mined transcripts accumulate here
│   ├── drafts/                     # drafts produced during grills
│   └── garden/                     # captured ideas (seeds)
├── inbox/                          # transcript drop zone (your tool exports here)
│   ├── granola/                    # created during Step 2 of setup, per tool
│   ├── otter/
│   └── ...
├── ONBOARDING.md                   # for non-technical users
└── README.md                       # this file
```

---

## Install

See [ONBOARDING.md](./ONBOARDING.md) for a step-by-step walkthrough designed for non-technical users.

Short version:

```bash
cd path/to/strategist
claude
```

Then in the Claude prompt:

```
/strategist
```

The strategist will detect your empty profile and start setup (Phase 1).

---

## Hard rules (universal, never broken)

1. **No fabrication.** Every drafted phrase traces to the user's audit material or their voice dump in this session.
2. **No em dashes (—).** AI tell. Use commas, periods, colons, parentheses.
3. **One open question at a time** during interviews and grills. No anchoring with "recommended answers." No multi-shape menus.
4. **Preserve seed titles verbatim.** No polishing for display.
5. **No auto-post.** Ever.
6. **Don't guilt.** Don't push quantity goals.
7. **Read the profile first, every invocation.**

---

## Status

v0.1 — first cut. The framework gets validated and sharpened by running it on a real user end-to-end before scaling to more.

---

## Built on

[Claude Code](https://claude.com/code).
