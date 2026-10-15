# The Weekly Snap

Fictional fantasy football site for deep leagues: rankings, start-sit calls, and
analysis. Built with Jekyll, hosted on GitHub Pages at
https://carsonde12.github.io/the-weekly-snap/

This is a fictional website created for educational purposes as part of
MKTG:4400 at the University of Iowa. It is not a real business.

## Where things live
- `_config.yml` — site title, description, plugins, URL structure
- `_posts/` — every blog post, one Markdown file each, named `YYYY-MM-DD-title.md`
- `_layouts/` — the HTML templates posts and pages are wrapped in (the
  fictional-site notice lives in `default.html`)
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
Commit the file with a message saying what changed and why, and the live site
updates within a minute or two.
