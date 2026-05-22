# Trend Sources

**Status:** TODO (set during Phase 2 sub-track B, or anytime via "configure trends")
**Last run:** NA (set by the strategist at the end of each `/strategist trends` invocation)

This file tells the strategist where to pull trending content from — Reddit, RSS feeds, Hacker News, etc. — when you run `/strategist trends`. The strategist fetches each source, maps items to your pillars, and proposes angles you could develop into content.

---

## Reddit subreddits

List subreddits to monitor. The strategist fetches `reddit.com/r/<name>/.json` (public, no auth) and pulls the top 20 posts from past week.

<<TODO: examples to prompt with based on common verticals:
- VC / startup space: r/Entrepreneur, r/startups, r/EntrepreneurRideAlong, r/YCombinator
- Marketing / content: r/marketing, r/SocialMediaMarketing, r/ContentMarketing
- AI / tech: r/MachineLearning, r/artificial, r/ChatGPT, r/LocalLLaMA
- Specific niches: depends on user's audience-of-one>>

Example shape after setup:
```
- r/Entrepreneur
- r/startups
- r/<your niche>
```

---

## RSS feeds

Any blog, newsletter, or news source with a public RSS feed. Paste full URLs.

<<TODO: examples:
- Hacker News front page: https://news.ycombinator.com/rss
- TechCrunch: https://techcrunch.com/feed/
- Substack publications in their space: <name>.substack.com/feed
- Industry-specific feeds>>

Example shape after setup:
```
- https://news.ycombinator.com/rss
- https://stratechery.com/feed/
- https://<industry-blog>.com/feed/
```

---

## Hacker News

Pull top stories from HN front page?

<<TODO: yes / no>>

If yes, strategist fetches the HN top 30 (via official JSON API) and filters against pillars.

---

## Product Hunt

Pull today's launches?

<<TODO: yes / no>>

If yes, strategist fetches PH daily list (via their public feed) — useful if "what's launching in AI/tools" is part of your content lane.

---

## Other sources (manual or custom)

For sources without RSS or open APIs (Twitter/X hashtags, TikTok trending, LinkedIn pulse), the strategist CAN'T auto-fetch reliably. Two workarounds:

- **Manual paste:** when you see something trending, paste it: `/strategist mine` + paste — strategist will check against pillars and propose seeds.
- **Tool integration:** if you use a tool that aggregates trends (Exploding Topics, Glasp, Pocket, Notion clipper), drop the export to `inbox/trends/` and the strategist processes it like a transcript.

<<TODO: list anything you want manually surfaced>>

---

## How the strategist uses this file

When user runs `/strategist trends`:
1. Read this file. Skip any source marked NA or SKIPPED.
2. Fetch each source (Reddit JSON, RSS, HN JSON) via WebFetch. ~30–60 sec total.
3. Parse: extract title + URL + score/age + summary.
4. Pre-filter by keyword match against pillar names (cheap regex).
5. For top 20 candidates: LLM-score against pillars + audience-of-one test.
6. Surface 5–10 with: title, source, pillar map, suggested angle.
7. User picks which to save to `profile/garden/` as seeds tagged `bucket: trend-angle, source: <reddit|rss|hn|ph>, url: <original>`.

The strategist does NOT auto-promote trends to post-worthy. Trend angles are STARTING POINTS — they still go through grill flow to become drafts.

---

## When to run `/strategist trends`

- **Weekly:** good rhythm. Strategist will proactively suggest "it's been 7 days since last trend hunt — want to run it?" via the no-arg verb.
- **When a pillar is starving:** if `pillar-tracking.md` shows a pillar with 0 hits in 14 days, the strategist suggests running trends filtered specifically to that pillar to find external triggers.
- **Whenever you feel out of ideas:** explicit user-triggered.
