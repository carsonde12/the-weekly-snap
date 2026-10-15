# Decision Log

Running notes on what was decided and why. Add to this as the semester goes —
it's the raw material for the "document and defend" part of the assignment.

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
`robots.txt` has to point to the sitemap at the longer path.

## Niche: deep-league fantasy football
Narrowed the angle to deep leagues (14-16 teams) after checking page-one
competition for generic fantasy rankings queries, which are dominated by ESPN
and NFL.com. Deep-league content exists on mid-size fantasy sites but
nobody builds a whole site around it, which is a more realistic opening.
The site description in `_config.yml` states the niche so it appears in meta
tags.

## SEO setup
- `jekyll-seo-tag` auto-generates per-page meta tags (title, description,
  Open Graph) instead of hand-writing them on every post.
- `jekyll-sitemap` auto-builds `sitemap.xml` so search engines can discover
  every post without manual submission.
- `jekyll-feed` auto-builds an RSS feed (`/feed.xml`) for readers/aggregators.
- `robots.txt` explicitly points crawlers to the sitemap.
- Permalinks are set to `/:categories/:title/` (e.g. `/rankings/week-1-qb-start-sit/`)
  instead of Jekyll's default date-based URL, so URLs contain readable,
  keyword-relevant text rather than just a date and slug.

## Visual design
Palette and type are grounded in the subject matter (turf green, chalk
off-white, a goalpost-gold accent) rather than a generic template look.
Anton (condensed, scoreboard-style) is used for headlines and the numbered
post list, echoing a "weekly power rankings" format. Archivo carries body
text for readability. A monospace face is used only in stat-table numeric
columns, where digits need to line up — not as decoration.

## Site structure
Two content categories — Rankings & Start-Sit, Analysis & Takes — each with
its own landing page, plus a numbered homepage feed of everything. Numbering
the post list doubles as a nod to the "power rankings" format the site is
about.

<!-- Add new decisions below as the semester progresses -->
