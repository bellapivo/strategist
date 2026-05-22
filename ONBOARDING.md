# Getting Started — for non-technical users

This is your fractional brand manager. It lives on your computer. You spend ~60 minutes once teaching it the basics, then it sharpens itself by reading your real conversations over time.

You don't need to know how to code. You need to follow five steps once. After that, you talk to it like a person.

---

## What you're installing

- **Claude Code** — an AI assistant that runs in your terminal (a text window on your computer).
- **The strategist** — a "skill" that teaches Claude how to act as your brand manager. It lives in this folder.

---

## Step 1 — Install Claude Code

**Important:** the strategist is built for **Claude Code** specifically. That's the developer-oriented version of Claude that can read files on your computer. It's different from the Claude chat app (claude.ai web or the Claude Desktop chat app) — those can't access local files, so the strategist won't work there.

You can run Claude Code three ways. Pick whichever you're most comfortable with:

### Option A — Terminal (most common)

1. Go to [claude.com/code](https://claude.com/code), install for Mac or Windows
2. Open your **Terminal** app (Mac: search "Terminal" in Spotlight; Windows: search "Terminal" in start menu)
3. Type `claude --version` — if you see a version number, you're good

### Option B — IDE extension (if you use Cursor, VS Code, or JetBrains)

1. Install the Claude Code extension from your IDE's marketplace
2. Sign in with your Claude account
3. Open the strategist folder in your IDE
4. The strategist skill loads automatically; you can chat in the IDE's Claude panel

### Option C — You already only use claude.ai web or Desktop chat

The strategist needs file access, so the full system won't work in those apps. You have two options:
- **Install Claude Code anyway** (Option A or B) and treat it as a separate tool just for your strategist sessions
- **Diminished version:** upload `SKILL.md` + the contents of `profile/` to a claude.ai Project as reference files. Claude will read them on every conversation in that Project. You lose: inbox scanning, auto-saving rewrites, the always-loaded CLAUDE.md, anything that writes files. You keep: voice-aware conversation, the strategist persona, your pillars in context. **Recommendation:** start with this if you're not technical, graduate to Claude Code when you want the full system.

You'll need a Claude account either way.

---

## Step 2 — Get the strategist folder

If your onboarder sent you a folder called `strategist`, save it somewhere easy — Desktop or Documents.

If cloning from GitHub:
```
git clone https://github.com/<owner>/strategist.git
```

---

## Step 3 — Open the folder in Claude Code

```
cd ~/Desktop/strategist
claude
```

Claude will start.

---

## Step 4 — Run setup (~60 minutes, one sitting)

Type:
```
/strategist
```

The strategist runs in **3 phases**.

### Phase 1 — INTAKE (~45 min): Who you are

Pure self-discovery. No tool setup here. 4 steps + synthesis:

1. **Bio interview (~20 min)** — 6 questions: who you are (incl. your name + platforms), why now + 12-month picture, who you want to reach, the thing not on your LinkedIn, what's off-limits, what content is FOR. **Use voice/dictation if you can.**
2. **Writing samples (~10 min)** — paste 3–5 things you've written.
3. **Speaking sample OR voice dump (~10 min)** — one podcast transcript, OR 5 minutes of you talking about your core topic.
4. **Voice north stars (~5 min)** — 2–3 people whose voice you want.

Then synthesis (~10 min): strategist proposes pillars + voice + audience-of-one + no-list **from your data**. You sign off. Profile locks. **A `CLAUDE.md` is generated at the project root** — from now on, Claude auto-loads as your strategist every time you open Claude Code in this folder.

**One more thing the strategist does at the end of synthesis:** it mines your audit material (everything you pasted during intake — writing samples, speaking sample, voice dump, dinner-party answers) and **seeds your garden with 5–10 starter content ideas** so you can start grilling on day 1. Without this, you'd walk out of intake with a locked strategy but an empty garden — and nothing to develop. The starter seeds give you something real to test the system with immediately.

### Phase 2 — BUILD YOUR ALWAYS-ON SYSTEM (~10–20 min, optional sub-tracks)

After intake locks, strategist walks you through wiring up the tools that feed it content over time. **Each sub-track is independent — skip any, add later.**

- **A. Meeting parser (~10 min)** — Granola, Otter, Apple Voice Memos auto-flow into `inbox/`. Every meeting becomes content raw material.
- **B. Trend watcher (~10 min)** — Reddit subreddits, RSS feeds, Hacker News, Product Hunt. Pull what's trending in your space, on demand.

You can do both right after intake, pick one, or skip and revisit anytime by saying "configure [meeting parser / trends]".

**On stats + sentiment tracking:** deliberately not built into v1. Useful eventually, but the right solution depends on your platforms, budget, and which numbers actually matter to you. We'll revisit after you've been operating for ~30 days and have real data to inform the choice.

### Phase 3 — OPERATE

This is the real job. The strategist scans every configured inbox on each invocation, mines new content, updates your pillar tracking, and surfaces what's worth your attention. You grill seeds, generate drafts, hunt trends, walk replies. Every 30 days the strategist proposes pillar refinement based on what's emerging in your actual conversations.

**Anything that doesn't apply, just say "NA."** No socials? NA. Never been on a podcast? NA. Faking answers makes the strategist worse.

---

## Step 5 — Day-to-day operation

After setup, you don't need to type `/strategist` every time. Claude auto-loads your context in this folder. You can:

- Say "I have an idea" → captured to garden
- Say "grill me on [title]" → deep develop into a draft
- Say "what should I post today?" → strategist surfaces what's ready
- Say "what's trending in my space?" → strategist runs `/strategist trends` and pulls from Reddit/RSS/HN/PH, proposes angles
- Paste a draft, ask "sound like me?" → voice check
- Paste a transcript, say "mine this" → strategist extracts pillar-aligned content moments
- Open Claude Code with new transcripts in your inbox → strategist offers to process them automatically

Type `/strategist` only when you want explicit verb routing (capture, grill, mine, generate, voice, trends).

---

## How "grill me on X" actually works (and what to do when an idea feels thin)

Grill is the most powerful verb. You say `grill me on [seed title]` and the strategist walks you through developing that idea into a real draft. Here's the flow:

1. **State the idea back to you.** "OK, the idea is: '[exact title]'. Ready?"
2. **Audience-of-one test (always question 1).** "Would [your audience-of-one] watch/save/share this? Why?" If you can't make it pass, the strategist proposes reshaping the angle or killing the seed. **Doesn't proceed past this gate unless you explicitly override.**
3. **One open question at a time** — format, the take (not the topic, the opinion), the moment (when did this come up for you?), the evidence, the boundary check against your no-list, the format mechanics.
4. **Drafts a final piece** Frankensteined from YOUR words — your audit samples, your voice dump, your answers in the grill. Nothing invented. No em dashes. Your voice.
5. **Shows you the draft.** You ship, edit, kill, or save for later.

### What to do when an idea isn't resonating or feels too thin

This is normal and expected. Not every captured idea has a real take buried in it. Three moves the strategist can pull:

**1. Ask for an interview.** Say *"interview me deeper"* or *"I don't have a take yet, pull it out of me."* The strategist will ask 3–5 deeper open questions to find the nugget — "when did you first notice this?" / "who pissed you off when you thought about this?" / "what's the version of this you'd tell a friend at 11 PM?" Voice-dump in response. The take is usually in there somewhere.

**2. Reshape the angle.** If the audience-of-one test fails, the seed isn't dead — the framing is. Say *"reshape this for [audience]"* and the strategist proposes 2–3 different angles using YOUR raw material.

**3. Kill or snooze.** Not every seed is post-worthy, and that's fine. Say *"kill it"* (moves to `bucket: kill`) or *"snooze for 30 days"* (resurfaces later, sometimes the take develops over time).

**The rule:** if there's no real take, the system would rather produce nothing than fabricate something that doesn't sound like you. Killing a seed isn't failure — it's discipline.

---

## The "always-on" part — how it actually works

**You don't need a background daemon. Here's the flow:**

1. **You connect a transcript tool** during setup (Step 2). Granola, Otter, etc. point their auto-export to `inbox/<tool>/`.
2. **The tool drops transcripts** into that folder as you have meetings.
3. **Whenever you open Claude Code in your strategist folder,** the strategist scans the inbox folder for new files. If there are any: "I see 3 new transcripts. Want me to process them?"
4. **Processing** = mining each transcript for pillar-aligned moments, saving the full transcript to your voice samples (so future drafts get sharper), and updating pillar tracking. Surfaces 3–10 candidate seeds per transcript.

From your perspective: open Claude Code in the morning with your coffee. Strategist absorbs everything from yesterday's meetings. You scan what got mined, save the good ones to your garden. Move on.

**No tool yet?** No problem. Skip Step 2 of setup. When you have a transcript, paste it: `/strategist mine` + paste. Same result, manual trigger.

---

## How to jot down ideas (anywhere, any time)

Content ideas strike when you're walking, in a meeting, at 2 AM. Three ways to capture them so the strategist sees them:

### 1. At-desk: `/strategist capture`

You're in Claude Code? Just type:
```
/strategist capture "the thing I just thought of"
```
Drops into your garden immediately, preserves your exact words, ready for grill later.

### 2. Away from desk: drop into `inbox/notes/`

**The strategist doesn't care what notes app you use** — it just reads any file (`.md`, `.txt`, even `.docx` if you can save it as text) inside `inbox/notes/`. You pick the workflow that fits your devices.

Common paths per platform:

- **iPhone + Mac (Apple ecosystem):** iOS Shortcuts can save Apple Notes or Voice Memo transcripts as text files to `inbox/notes/` automatically. ~10 min one-time setup.
- **Android:** Google Keep + Tasker can mirror notes to a folder. Or use Drive + a sync script.
- **Notion:** export a specific database/page → sync to `inbox/notes/`. Or use Notion's API + a small automation.
- **Bear, Obsidian, Bear, plain Markdown:** these already save to folders. Set the save location to `inbox/notes/` or symlink your existing folder.
- **Email-to-self:** Gmail filter that saves emails with subject "💡" (or whatever marker) to a folder, synced to `inbox/notes/`. Platform-agnostic.
- **Voice memo on any phone:** record → transcribe (Otter, ScreenApp, free apps) → save transcript to `inbox/notes/`.
- **No automation at all:** just keep a running list anywhere — phone notes, paper, a Google Doc. Once a week, paste the whole thing into Claude Code with `/strategist mine`. Same result.

The point: every modern notes app has *some* path to "save to a folder." Whatever yours is, point it at `inbox/notes/`. If you can't figure it out, ask the strategist to help you set it up.

### 3. Anything you can paste, the strategist can mine

If automation feels like too much: paste anything into chat. A long voice memo transcript, last week's journal, a brain dump you typed on your phone, screenshots of your own old tweets. Tell the strategist "mine this" and paste. Works the same as the automatic inbox.

---

## How trend hunting works

Once you've configured trend sources in Step 2 of setup, you can run trend hunts whenever:

```
/strategist trends
```

The strategist will:
1. Pull recent posts from your configured subreddits, RSS feeds, HN, and PH
2. Filter against your pillars + audience-of-one test
3. Surface 5–10 trend angles with:
   - The original title + link
   - Which pillar it maps to
   - A suggested angle (1 sentence — what YOU could say about it)
4. You pick which to save to your garden as seeds tagged `trend-angle`

Takes ~30–60 seconds. Strategist will also proactively offer this every 7 days when you open Claude Code ("haven't checked trends in a week — want me to pull?").

**Important:** trend angles are STARTING POINTS, not finished posts. Each one still goes through the grill flow to become a draft in your voice.

---

## What the strategist will NOT do

- **Auto-post.** Ever. You always review and ship manually.
- **Make up takes you didn't say.** Every line traces back to your own words.
- **Use em dashes** unless your voice profile explicitly embraces them.
- **Push you to post when you're not in the mood.**
- **Recommend formats you said you wouldn't do.**
- **Lock pillars permanently.** Pillars are a hypothesis that sharpens from observation.

---

## What Claude CAN and CAN'T do

- ✅ Read text you paste
- ✅ Fetch text from URLs you give it (with permission prompts)
- ✅ Read transcript files from your inbox folder
- ✅ Save your content to files in `profile/`
- ❌ **Watch videos.** Give it transcripts or captions, not video files.
- ❌ **Listen to audio.** Same — transcripts only.
- ❌ **Log into your accounts.** It fetches public pages but won't scrape DMs or analytics.

---

## Permission prompts you'll see

First few invocations, Claude Code will ask permission for:
- **Read/Write/Edit** on `profile/` and the project root — needed to save your data and generate CLAUDE.md
- **Bash** for scanning the inbox folder and moving processed files — needed for transcript processing
- **WebFetch** for URLs you provide — needed to pull LinkedIn / Substack pages

Approve these. Reject anything unrelated.

---

## What success looks like in 30 days

- Setup is locked.
- You've processed ~10 transcripts (or pasted them manually).
- The first **pillar refinement** has happened: the strategist proposed promoting an emergent topic and/or demoting a pillar that wasn't getting hits.
- Your voice profile has at least 2 logged rewrites — the strategist is learning how you edit.
- You've shipped at least 4 pieces of content built through the grill flow.

If you're not there in 30 days, something's off. Tell the strategist: "audit my last 30 days, where did I fall off?"

---

## When something goes wrong

- **"It feels generic" / "this doesn't sound like me"** — tell it exactly, with the line you don't like. It logs the rewrite and updates voice profile.
- **"It's asking too many questions at once"** — push back: "one at a time."
- **"It suggested something on my no-list"** — flag it. No-list is sacred. The strategist must check it before showing drafts.
- **"My inbox folder isn't getting processed"** — check that your tool is actually exporting (look in `inbox/<tool>/` for files). Tell the strategist: "scan my inbox" to force a check.

---

## One more thing

The strategist is opinionated. It will push back on you. It will demote pillars when the data says they're dead. It will surface emergent topics you didn't know you cared about.

Let it disagree. Argue back. That's the whole job.
