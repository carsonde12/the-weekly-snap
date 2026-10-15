# The Weekly Snap

Fantasy football blog — rankings, start-sit calls, and analysis for deep
leagues. Built with Jekyll, hosted on GitHub Pages at
https://carsonde12.github.io/the-weekly-snap/

## Where things live
- `_config.yml` — site title, description, plugins, URL structure
- `_posts/` — every blog post, one Markdown file each, named `YYYY-MM-DD-title.md`
- `_layouts/` — the HTML templates posts and pages are wrapped in
- `assets/css/style.css` — all site styling
- `index.html`, `rankings.html`, `analysis.html`, `about.md` — the site's pages
- `DECISIONS.md` — running log of decisions made and why (for the assignment writeup)

## Adding a new post
Create a new file in `_posts/` named `YYYY-MM-DD-a-short-title.md`, with
front matter like this at the top:

```
---
title: "Your Post Title"
categories: [rankings]
---
```

Use `categories: [rankings]` or `categories: [analysis]` depending on which
section it belongs to. Write the post itself in Markdown below the `---`.
Commit/push the file (or upload it on GitHub) and the live site updates
automatically within a minute or two.
