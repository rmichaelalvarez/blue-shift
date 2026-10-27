# Why the Lead Changes: Simulating Blue and Red Shifts in Vote Counting

An interactive teaching simulation of why election-night leads change as late mail ballots and provisional ballots are counted. Users can change who votes which way, how large and how young each batch of ballots is, and the order the batches are counted. They then watch the running margin move ("Explore"), or try to call a race as reports arrive ("Call the race").

**Author:** R. Michael Alvarez, California Institute of Technology
**Version:** 1.0 (October 27, 2026)

## Background

The simulation accompanies:

> Li, Yimeng, Michelle Hyun, and R. Michael Alvarez. 2022. "Why Do Election Results Change after Election Day? The 'Blue Shift' in California Elections." *Political Research Quarterly* 75(3): 860–874. https://doi.org/10.1177/10659129211033340

All voters, batches and rounds are invented for teaching. They are not real election results or forecasts. The "California-style" and "Pennsylvania 2020-style" scenarios illustrate those counts and are not fitted to real data.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole application: one self-contained page with no build step. It loads fonts from Google Fonts, collects no data and runs entirely in the browser. |
| `social-preview.png` | 1200 × 630 image used when the link is shared on social media or in chat apps. |
| `README.md` | This file. |
| `LICENSE` | MIT License. |

## Publishing with GitHub Pages

1. Put these four files at the top level of the repository.
2. In the repository, open **Settings → Pages**. Set **Source** to **Deploy from a branch**, choose **main** and **/ (root)**, then **Save**.
3. After a minute or two, the site appears at `https://<username>.github.io/<repository-name>/`.
4. Once you know that address, edit the `og:image` line near the top of `index.html` and replace `social-preview.png` with the full address. Many sites only show the preview image when given an absolute URL, for example `https://rmichaelalvarez.github.io/blue-shift/social-preview.png`.

## Shareable links

The **Copy link** buttons make links that open the page in a particular state:

- `#explore?preset=ca`: a ready-made scenario (`ca`, `rev`, `pa` or `red`)
- `#explore?o=ca&y=60&a=45&e=40,20,0&i=30,40,0&l=22,65,0&p=8,75,0`: a custom scenario
- `#game?round=3`: a particular round of "Call the race." Every user who opens the same round sees the same race.

## How the model works

- There are 500,000 ballots in four batches: early mail, in person, late mail and provisional.
- Each batch has a share of all ballots, a share of voters under 45, and an optional "party strategy" effect, in points toward one party.
- A batch's Democratic share is (share under 45 × Democratic share of under-45 voters) + (share 45 and older × Democratic share of older voters) + the party strategy effect.
- Batches are reported in the chosen order, split into 1–4 reports each.
- In "Call the race," rounds 1–8 are generated from a fixed random seed. Each report adds up to ±1.2 points of variation. Every round's final margin is between 0.3 and 3.5 points.

## How to cite

Alvarez, R. Michael. 2026. *Why the Lead Changes: Simulating Blue and Red Shifts in Vote Counting* (version 1.0). Interactive web simulation, California Institute of Technology.

## License

Released under the MIT License (see `LICENSE`). You are free to use, copy, modify and share this simulation, including in your own courses. Keep the copyright and license notice.

## AI assistance

The code and text were drafted with Claude Opus 5.5 (model ID `claude-opus-5-5`), an AI model made by Anthropic, working with the author.
