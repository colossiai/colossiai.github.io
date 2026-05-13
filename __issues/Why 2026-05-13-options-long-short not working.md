```

⏺ Found it. The post is not broken — it's a Jekyll/GitHub Pages future-date issue.

  Timeline:
  - You committed 6611a5a at 2026-05-13 00:20:08 +0800 (= 2026-05-12 16:20 UTC)
  - Frontmatter says date: 2026-05-13 → Jekyll parses this as 2026-05-13 00:00:00 UTC
  - At the moment GitHub Pages built the site, that post date was ~7h40m in the future → GitHub Pages skips future-dated posts by default (no --future flag)
  - Now it's 2026-05-13 01:53 UTC (past the post's effective time), but GitHub Pages doesn't auto-rebuild on a schedule — it only rebuilds on push

  The other May 10 posts published fine because by the time they were committed, May 10 00:00 UTC was already in the past.

  Fix — any one of these:

  1. Easiest — push any trivial commit (e.g., edit the README) to trigger a rebuild. The post will now appear since 00:00 UTC has passed.
  2. Add an explicit past time to the frontmatter and push:
  date: 2026-05-13 00:00:00 +0800
  2. (00:00 HKT = 16:00 UTC May 12 — safely in the past at commit time)
  3. Set timezone: Asia/Hong_Kong in _config.yml so future bare-date posts are interpreted in HKT, not UTC.


```