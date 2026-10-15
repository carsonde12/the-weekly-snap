# Decision Log

Running notes on what was decided and why. Add to this as the semester goes.
It's the raw material for the "document and defend" part of the assignment.

## Platform: Jekyll on GitHub Pages
Chose Jekyll over hand-written HTML because the site needs weekly recurring
posts all season. Jekyll turns each post into a short Markdown file and
auto-applies a consistent template, instead of duplicating a full HTML page
by hand every week. It's natively supported by GitHub Pages, so there's no
separate hosting service or build step to manage.

## Repo name and URL: the-weekly-snap (project site)
Named the repository `the-weekly-snap` instead of the default
`carsonde12.github.io`, so the site lives at
`carsonde12.github.io/the-weekly-snap/`. The name matches the site brand and
is more memorable than a bare username URL. The tradeoff is that Jekyll needs
`baseurl: "/the-weekly-snap"` in `_config.yml` so CSS and links resolve, and
Google only reads `robots.txt` at the root of `carsonde12.github.io`, so the
file at `/the-weekly-snap/robots.txt` loads but crawlers ignore it. The
sitemap can still be submitted in Search Console.

## Niche: deep-league fantasy football
Narrowed the angle to deep leagues (14-16 teams) after checking page-one
competition for generic fantasy rankings queries, which are dominated by ESPN
and NFL.com. Deep-league content exists on mid-size fantasy sites but
nobody builds a whole site around it, which is a more realistic opening.
The site description in `_config.yml` states the niche so it appears in meta
tags.

## Required fictional-site notice
The class requires a fixed notice at the top and in the footer of every page.
It is written into `_layouts/default.html`, which every page and post uses, so
a new page cannot go live without it. The text is copied word for word from
the assignment.

## Content: written by the AI model, grounded in public reports
All content is written by the AI model, as the assignment requires. The
rankings are opinion. Player roles, matchups, byes, and injury statuses come
from public reports dated October 14-15, 2026, and each post says its
information is current through that date. Posts avoid invented statistics; the
only made-up numbers are labeled illustrative. The About page uses an invented
editor persona, labeled as invented.

## Content structure
Two categories, each with a landing page: Rankings & Start-Sit (weekly,
time-sensitive) and Analysis & Takes (evergreen strategy). The six posts each
target a different topic so no two pages compete for the same query: waiver
adds, flex rankings, and streaming (rankings); league math, waiver strategy,
and bye-week planning (analysis).

## SEO setup
- `jekyll-seo-tag` auto-generates per-page meta tags (title, description,
  Open Graph) instead of hand-writing them on every post.
- `jekyll-sitemap` auto-builds `sitemap.xml` so search engines can discover
  every post without manual submission.
- `jekyll-feed` auto-builds an RSS feed (`/feed.xml`) for readers/aggregators.
- `robots.txt` explicitly points crawlers to the sitemap.
- Permalinks are set to `/:categories/:title/` (e.g. `/rankings/week-6-streaming-rankings-deep-leagues/`)
  instead of Jekyll's default date-based URL, so URLs contain readable,
  keyword-relevant text rather than just a date and slug.
- Title tags, meta descriptions, anchor text, and image alt text are still to
  be set from the keyword plan (Deliverable 2, on-page plan).

## Visual design
Palette and type are grounded in the subject matter (turf green, chalk
off-white, a goalpost-gold accent) rather than a generic template look.
Anton (condensed, scoreboard-style) is used for headlines and the numbered
post list, echoing a "weekly power rankings" format. Archivo carries body
text for readability. A monospace face is used only in the first column of
tables, where short numbers and labels need to line up.

## Mobile layout
Tables use a fixed layout with wrapping text and are limited to two to four
short columns, so nothing needs sideways scrolling on a phone. Rankings are
written as numbered lists rather than wide tables.

<!-- Add new decisions below as the semester progresses -->
