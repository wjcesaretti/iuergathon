# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static HTML fundraising page for IU Rowing Club's Spring 2026 season, deployed at [iuergathon.com](https://iuergathon.com) via GitHub Pages. There is no build step, no package manager, and no framework — just a single `index.html` file with all CSS and JS inline.

## Deployment

Push to the `main` branch on GitHub. GitHub Pages auto-deploys. The `CNAME` file maps the custom domain `iuergathon.com`.

## Updating the Fundraising Total

The live amount raised is fetched from a Google Sheets CSV URL in `index.html:530`. The sheet must publish row 2 (column A) as the current dollar total. The `GOAL` constant is set to `10000` at line 527.

To change the goal or hardcode a fallback amount, edit those values in the `<script>` block at the bottom of `index.html`.

## Key Sections in index.html

- **Thermometer / football field progress bar** (~lines 367–408): animated SVG football field showing fundraising progress. Milestone markers at $0, $2,500, $5,000, $8,000, and $10,000 (Touchdown).
- **Donation tiers** (~lines 447–494): six tiers ($25–$1,000+), all linking to the same Zeffy donation form.
- **Ergathon section**: lives in `ergathon-snippet.html` — this is a standalone HTML snippet (not included in `index.html` by default) for the team's 1,000,000m rowing event. Date and location are TBD.
- **IU Day section** (~lines 496–506): currently has a duplicated heading (both "Ergathon" and "IU Day" headings show April 22).

## Design System

All styles are inline in `<style>` at the top of `index.html`. CSS custom properties (`:root`) define the color palette:
- `--crimson` / `--crimson-dark` / `--crimson-light`: IU brand red
- `--gold` / `--gold-dim`: accent gold
- `--cream` / `--cream-light` / `--cream-dark`: off-white text
- `--dark` / `--dark-card` / `--dark-border`: dark background tones
- `--field-green`: football field green

Fonts: **Oswald** (headings, labels, numbers) and **Source Sans 3** (body) from Google Fonts.

## Images

All images are in `/images/`. Hero background is `images/team-modified copy.jpeg` (set in `.hero-bg` CSS). Several `TODO` comments in the HTML note where to swap in updated photos.
