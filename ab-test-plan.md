# A/B test plan: home page headline

**Site:** The Weekly Snap, a fictional site for MKTG:4400, University of Iowa, Fall 2026. https://carsonde12.github.io/the-weekly-snap/
**Author:** Carson DeSaulniers
**This version written:** 17 November 2026. No trial has been run as of this commit.

> This is a fictional website created for educational purposes as part of MKTG:4400 at the University of Iowa. It is not a real business.

## Change from the first version of this plan

The first version of this file (committed earlier, still in the repository history) tested a Google search-result title shown to AI visitors as a text snippet. The D3 handout requires the visitor to see the page itself, and a variant page B that stays out of search. This version replaces it before any trial has been run. Nothing else about the test was decided after seeing data, because there is no data yet.

## Page and the single element changed

- **Page:** the home page. Version A is the live page, https://carsonde12.github.io/the-weekly-snap/
- **Element:** the main headline (the h1). Nothing else differs: same intro paragraphs, same links, same post list, same layout and fictional-site notice.
- **Version A (current):** "Fantasy football for leagues where the waiver wire is empty"
- **Version B (variant):** "Fantasy football advice built for 14- and 16-team leagues"
- **Where B lives:** https://carsonde12.github.io/the-weekly-snap/ab-test/home-b/ (file `ab-home-b.html`)
- **Protecting rankings:** B carries a noindex robots tag, is excluded from sitemap.xml, is not linked from any page, and is not blocked in robots.txt (so a search engine can read the noindex).

## Why this element

The home page is the first page most visitors see, and the headline is the first thing they read. The site targets managers in 14- and 16-team deep leagues, a narrow audience. Version A describes that audience with an image (an empty waiver wire) and expects the reader to work out that it is for them. Version B names the audience outright with the league sizes. Both headlines make the same promise, so the test isolates how directly the headline states who the site is for.

## Hypothesis

A larger share of AI visitors playing a 16-team league manager will say they would bookmark and check the site weekly when they see Version B than when they see Version A. The reasoning is that a reader decides within seconds whether a page is about their situation, and a headline that names "14- and 16-team leagues" makes that match immediate. The prediction can be wrong: if the intro paragraph already makes the audience clear, or nearly every visitor says yes to either headline (a ceiling effect), B will show no gain.

## Visitor, model, prompt

- **Visitor:** an AI model given the persona below. Every trial is a brand-new chat with memory switched off. No chat sees more than one version.
- **Model:** Claude Sonnet 5.5 in the Claude app, free plan, memory off, web search off, thinking off. The same model and settings are used for every trial, and the model name and date are recorded on every row of the trial log.
- **Page shown:** the full visible text of the page, copied from the live page (Ctrl+A, Ctrl+C) at the address of Version A or Version B and pasted the same way in every trial.
- **Exact prompt, identical in every trial except the pasted page:**

      You are a college student in Iowa who plays in a 16-team PPR fantasy football league and often cannot find useful players on the waiver wire. You have just landed on the web page below. Read it and decide whether you would bookmark this site and check it every week this season to help with your lineup. Answer yes or no, then give one sentence of reasoning.

      [paste the full visible text of the page]

## Assignment

Chance decides each trial's version before anything runs. I shuffled 50 A and 50 B into one sequence with Python's random generator (`random.Random(20261117).shuffle`), which gives exactly 50 per version. The sequence is fixed below and is also stored in the trial log. Trials are run in this order, and no trial is reassigned.

      1-10   B B A B A B A A B A
     11-20   B B A B A B A B A A
     21-30   A B A A B B A B B A
     31-40   A A A B B B B B B A
     41-50   B B B A B B B B A B
     51-60   A A B A A B B B B B
     61-70   A A B A B A B A B A
     71-80   A B A A B B B B A A
     81-90   B B B A B A A A A A
     91-100  B A B A A A A A A A

## Primary outcome

One question, answered for every trial: would the visitor bookmark the site and check it weekly. An answer that starts with "yes" scores 1. Everything else, including "no" and "maybe", scores 0. The scoring rule is set now, before any answer is seen. The full raw answer is saved for every trial, and no trial is ever rerun or dropped.

## Sample size and dates

- **Sample:** 50 trials per version, 100 in total, all collected before any analysis. No stopping early, no peeking at the running tally.
- **Schedule:** about 25 trials per day, Tuesday 17 November to Friday 20 November 2026. I expect to reach 100 by Friday 20 November and analyse once, over that weekend.
- **Power, honestly:** with 50 per version, a test at 5 percent significance and 80 percent power can reliably detect only a gap of roughly 30 points in the yes share. A smaller real difference will probably come out not significant, and that would not prove there is no effect.

## Comparison and what counts as support

I compare the yes share in B with the yes share in A, using a two-proportion z test (two-sided) on the difference, with a 95 percent confidence interval. Support for the hypothesis means B's yes share is higher than A's and the two-sided p value is below 0.05. If B is higher but p is 0.05 or more, I report the test as inconclusive and too small to tell, not as a win. If B is the same or lower, the hypothesis is not supported. Decision: roll out B only on a supported result, otherwise keep A.

## What this test can and cannot tell me

It can show whether a model, told who to be, responds differently to the two headlines, and the one-sentence reasons often show why. It cannot show what real fantasy football managers would do. AI visitors answer far more alike than a crowd, and a result may not hold for another model or a reworded prompt.

## Records kept

`ab-test-log.csv` (added after the trials): one row per trial with the trial number, version, date, model, full output and score, plus a dated log of anything that went wrong or changed. Screenshots of both versions are saved with the report.

## AI use

Claude (Anthropic) helped draft this plan and build the variant page and the analysis spreadsheet. The test choices are mine.
