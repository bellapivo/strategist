# Transcript Sources

**Status:** TODO (set during Phase 2 sub-track A — meeting parser setup)

This file tells the strategist where to look for new transcripts. When the inbox folder gets new files (from auto-export by your tool), the strategist processes them next time you open Claude Code in this folder.

---

## Configured sources

<<TODO: filled in during setup>>

Example shape after setup:

```
- Tool: Granola
  Inbox folder: inbox/granola/
  Setup: configured (auto-export from Granola Settings → Notes)
  Last scan: 2026-05-18

- Tool: Otter
  Inbox folder: inbox/otter/
  Setup: manual-paste-only (no auto-export configured)
  Last scan: NA

- Tool: Apple Voice Memos
  Inbox folder: inbox/voice-memos/
  Setup: configured via Shortcuts automation
  Last scan: 2026-05-17
```

---

## How the strategist uses this file

On every invocation:
1. Reads this file for inbox folder paths
2. Scans each configured folder for new files (anything not yet in `archived/`)
3. If new files exist: offers to process before anything else
4. After processing: moves files to `<folder>/archived/` so they're not re-processed

If `Setup: manual-paste-only` → no folder scan, user pastes via `/strategist mine`.

---

## Adding a new source later

Just say "connect [tool name]" — strategist walks you through it and updates this file.

---

## Universal: no tool configured (skipped)

If you skipped Step 2 of setup, this file is SKIPPED. Paste transcripts manually with `/strategist mine` whenever you have them. When you adopt a tool, run setup again or just tell the strategist.
