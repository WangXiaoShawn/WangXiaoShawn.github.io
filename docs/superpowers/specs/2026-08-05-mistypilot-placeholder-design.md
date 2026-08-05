# MistyPilot Placeholder Project Page — Design

**Date:** 2026-08-05
**Status:** Approved

## Goal

Reserve a public project page for MistyPilot on the academic homepage before the
paper and code are released. The page must look like it belongs to the site, and
turning it into the real page later must be a matter of replacing text and
un-disabling links — not rebuilding.

## Scope

Three changes:

1. `MistyPilot.html` — new standalone project page.
2. `files/pubs/MistyPilot.svg` — generated placeholder thumbnail.
3. `index.html` — one new publication row at the top of Selected Research.

Nothing else changes. No News entry.

## 1. MistyPilot.html

Structural clone of `AutoMisty.html` (Bulma + NeRFies-derived template), so the
two pages render identically apart from content.

| Section | Content |
| --- | --- |
| Nav | `← Back to Homepage` → `./index.html` |
| Title | MistyPilot: Enabling Social-Robot Control through Multi-Agent LLM Skill Orchestration |
| Authors | **Xiao Wang\***, **Lu Dong\***, Ifeoma Nwogu, Srirangaraj Setlur, Venu Govindaraju |
| Affiliation | State University of New York at Buffalo |
| Footnote | `* Equal contribution.` |
| Links | Paper / arXiv / Code, all rendered disabled |
| Teaser | `./files/pubs/MistyPilot.svg` |
| Abstract | "Abstract coming soon." |
| BibTeX | `@misc{wang2026mistypilot, ...}` placeholder |
| Footer | NeRFies template attribution, as on the other pages |

Xiao Wang links to `https://wangxiaoshawn.github.io/` and Lu Dong to
`https://dongludeeplearning.github.io/`, matching `AutoMisty.html`. The remaining
authors are plain text — `AutoMisty.html` wraps them in empty `href=" "` anchors,
which produces dead links; that is not copied.

**Disabled links.** Each of the three buttons uses Bulma's `is-static` class with
`pointer-events: none`, labelled `Paper (Coming Soon)`, `arXiv (Coming Soon)`,
`Code (Coming Soon)`. Publishing = replace the label, swap `is-static` for
`is-dark`, add the real `href`. No dead `href="#"` links ship.

## 2. files/pubs/MistyPilot.svg

Hand-written SVG rather than a raster placeholder: a few KB of text, renders in
both `background-image` and `<img>`, and needs no image toolchain.

- `viewBox="0 0 560 300"` — matches the 280×150 `.row-media` box at 2× so it
  stays crisp; `background-size: contain` handles the fit.
- Dark slate background, rounded corners, `MistyPilot` in large type, `Coming
  Soon` beneath it in muted small caps.
- Uses generic font families only (no webfont fetch).

When the real figure exists, drop `files/pubs/MistyPilot.png` in and update the
two references.

## 3. index.html

Insert one `.publication.row.clearfix` block immediately before the AutoMisty
block (line ~162), so MistyPilot appears first under Selected Research.

- Thumbnail: `files/pubs/MistyPilot.svg`
- Title link → `MistyPilot.html` (`target="_blank"`, matching siblings)
- Author line identical to the project page
- Venue line: *Preprint, 2026*
- Buttons: a single `Project Webpage` → `MistyPilot.html`. No DOI/PDF/BibTeX
  buttons, since every one of them would be a dead link today.

## Verification

Open `index.html` and `MistyPilot.html` in a browser and confirm:

- the new row is first under Selected Research and its thumbnail renders;
- the title link and Project Webpage button both reach `MistyPilot.html`;
- the three Coming Soon buttons are visibly inert and unclickable;
- `← Back to Homepage` returns to `index.html`;
- the page reflows correctly below the site's 800px mobile breakpoint.

## Non-goals

- No News entry.
- No real abstract, BibTeX, video, or figure.
- No changes to other project pages.
