# Pillar Tracking

**Status:** ACTIVE (initialized at synthesis lock; updated continuously by the strategist)

This file tracks how often each pillar shows up in mined transcripts AND surfaces emergent topics that aren't yet pillars but should be. Updated automatically by the strategist on every mining session.

The refinement flow reads this file every 30 days or every 10 mined transcripts to propose pillar promotions/demotions.

---

## Locked pillars

(Initialized from `strategy.md` at synthesis lock; updated only via refinement flow.)

| Pillar | Hits last 30d | Hits all-time | Last mined | Trend |
|---|---|---|---|---|
| <<Pillar 1 name>> | 0 | 0 | NA | new |
| <<Pillar 2 name>> | 0 | 0 | NA | new |
| <<Pillar 3 name>> | 0 | 0 | NA | new |

**Trend definitions:**
- `new` — locked <14 days ago, not enough data
- `active` — ≥3 hits in last 30 days
- `declining` — 1–2 hits in last 30 days
- `dormant` — 0 hits in last 30 days

---

## Emergent topics (not yet pillars, but appearing in transcripts)

| Topic | Hits last 30d | First seen | Notes |
|---|---|---|---|
| <<empty until mining surfaces patterns>> | | | |

**Promotion threshold:** any emergent topic with ≥5 hits in 30 days gets flagged for pillar promotion at next refinement check.

---

## Refinement history

| Date | Changes made |
|---|---|
| <<filled in after each refinement>> | |

---

## Last refinement check

**Date:** <<initialized to synthesis-lock date>>
**Days until next:** 30 from last (default) OR triggered immediately when ≥10 new transcripts mined.

**Transcripts mined since last refinement:** 0

This counter increments by 1 in the "Process inbox" flow for every transcript/note processed. Reset to 0 after each refinement check runs. The strategist gates the proactive refinement prompt on this counter ≥10 OR `Last refinement check` ≥30 days ago.
