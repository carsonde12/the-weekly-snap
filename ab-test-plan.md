# A/B test plan: search-result title for the Top 150 page

**Site:** The Weekly Snap (fictional site for MKTG:4400, University of Iowa, Fall 2026). https://carsonde12.github.io/the-weekly-snap/
**Author:** Carson DeSaulniers
**Plan written:** 9 November 2026, before any trial is run

> This is a fictional website created for educational purposes as part of MKTG:4400 at the University of Iowa. It is not a real business.

## Decision

Which title should the Top 150 PPR rankings page use in its search-result listing: the current generic title (A), or one that names the audience, deep leagues (B)?

## Hypothesis

If the search-result title says "Deep League" instead of "Fantasy Football", then a larger share of simulated deep-league players will say they would click the result, because the title tells them the rankings are built for their league size.

## Unit

One AI visitor. Each trial is one brand-new chat with memory switched off. No chat sees more than one listing.

## Versions

Only the first line (the title) differs. The web address and the description are identical and word for word.

**Version A, control (current title)**

    Top 150 Fantasy Football Rankings (PPR) | The Weekly Snap
    carsonde12.github.io › the-weekly-snap › top-150-ppr-rankings
    Top 150 fantasy football rankings for PPR leagues, in tiers and adjusted for 14- and 16-team deep leagues. Current through Week 9, 2026.

**Version B, treatment**

    Top 150 Deep League Rankings (PPR) | The Weekly Snap
    carsonde12.github.io › the-weekly-snap › top-150-ppr-rankings
    Top 150 fantasy football rankings for PPR leagues, in tiers and adjusted for 14- and 16-team deep leagues. Current through Week 9, 2026.

The listing text is frozen as written above for the whole test, even if the live page is updated to a later week.

## Population

AI visitors told to act as a college student in Iowa who plays in a 16-team PPR league and is searching for rankings. They are not real customers (see limits below).

## Prompt, identical in every trial

    You are a college student in Iowa playing fantasy football in a 16-team PPR league. You are searching Google for player rankings before you set your lineup. Read this search result and decide whether you would click it. Answer yes or no, then give one sentence of reasoning.

    [paste the text of version A or version B]

## Held fixed for all trials

- The prompt wording, word for word
- How the listing is given: pasted text, never typed by hand
- One AI app and one model, the same for every trial. The app, model name, plan, date and settings (memory off, web search off) are written on every row of the trial log.
- A new chat for every trial, memory off, chat closed afterwards
- Trials run in the order of the assignment sheet, with no tallying while running

## Assignment

Chance decides each trial's version before anything runs. In a spreadsheet, row 2 to row 101 each get `=IF(RANDBETWEEN(0,1)=0,"A","B")`. The results are then copied and pasted as values so they stop changing, and the trials are run in row order. Group sizes may come out unequal (for example 47 and 53). The analysis handles that.

## Outcome and scoring rule (decided before any answers are seen)

Primary outcome: would the visitor click. An answer that starts with "yes" scores 1. Everything else, including "no" and "maybe", scores 0. The full raw answer is saved in the log, and no trial is ever rerun.

## Size and length

- Target: 50 trials per version, 100 trials in total, which meets the course minimum of 50 per version.
- Run over several days in the window 10 to 16 November 2026, with the same model throughout. The test launches no later than Tuesday 17 November 2026.
- Honest note on power: with about 50 per version, a test at 5 percent significance and 80 percent power can reliably detect only a gap of roughly 30 points in the yes share. A smaller real difference will probably come out "not significant", and that would not prove there is no effect.

## Analysis (run once, after all trials are in)

Using the eight spreadsheet cells from Session 18: visitors and yes counts for each version, the difference in yes share (B minus A), the standard error, z, and the two-sided p value. I will report the difference in points and the relative lift, and the 95 percent interval (difference ± 1.96 × standard error). The same numbers will also be requested from an AI model and compared against my spreadsheet, and my spreadsheet wins any disagreement.

## Decision rule (set in advance)

| Result | Action |
|---|---|
| B's yes share is higher and p < 0.05 | Change the live title to B |
| B's yes share is higher but p is 0.05 or more | Keep A for now and say the test could not tell them apart; consider a larger test |
| B's yes share is the same or lower | Keep A |

## What this test can and cannot tell me

It can show whether a model, told who to be, reacts differently to the two titles, and the one-sentence reasons often show why. It cannot show what real searchers would click or buy. AI visitors answer far more alike than a crowd, and the result may not hold for another model or a reworded prompt.

## Files

- `ab-test-plan.md`: this plan, committed before the first trial
- `ab-test-log.csv` (added later): one row per trial with trial number, version, answer, score, full output, app, model, plan, date and settings

## AI use

Claude (Anthropic) helped draft this plan. The test design choices are mine and I checked them against Sessions 16 to 18.
