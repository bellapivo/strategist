# Engagement preferences

**Status:** TODO (set during Phase 2 close — the reminder loop question)

How the strategist pushes content to the user, and where. Without push, pull-only systems fizzle.

---

## Cadence

<<TODO: one of daily / weekly / calendar / none / hybrid>>

- `daily` — one post idea every morning at the configured time
- `weekly` — Sunday batch of what to post this coming week
- `calendar` — strategist drops a 15-min "post today" block on the user's calendar at their filming time, with the idea inside the description
- `none` — fully pull, user comes to the strategist when they have time
- `hybrid` — combination, e.g. daily + Sunday digest

---

## Channel

<<TODO: where the push lives — email / calendar / slack / osx-notification / handoff-to-system / other>>

- `email` — push gets piped to a sendmail / mailgun / SES integration the user wires up
- `calendar` — strategist's output gets dropped into a Google Calendar event via the user's calendar agent
- `slack` — DM to user via webhook or Slack API
- `osx-notification` — `osascript` triggers a native Mac notification with the title/body
- `handoff-to-system` — push content written to a file path the user's existing assistant (COS, EA agent, etc.) reads as input
- `other` — user-described

---

## Time

<<TODO if cadence is daily/weekly/calendar — e.g. "8am" for daily, "Sunday 7pm" for weekly, "30 min before filming block" for calendar>>

---

## Handoff path (only if channel = handoff-to-system)

<<TODO: absolute path where the push markdown gets written. Default suggestion if user has a Vault: `~/Desktop/Vault/_inbox/strategist-daily.md`. The user's existing system reads this file and handles delivery to wherever the user actually sees it.>>

---

## Setup status

<<TODO: PENDING (user still needs to wire up delivery on their end) → CONFIGURED (delivery path tested and working)>>

---

## How the strategist uses this file

- **Daily push flow** reads this file on every push run. If `cadence: none`, push exits silently.
- **At setup** (Phase 2 close), strategist captures preference and writes this file.
- **Anytime** user can say "change how you reach me" and strategist updates this file.
- **No delivery from the strategist itself.** Strategist writes content to `profile/pushes/YYYY-MM-DD.md` and (if `handoff-to-system`) to the configured handoff path. Actual delivery is the user's system's job. Per the no-auto-send hard rule.
