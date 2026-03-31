# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

"The Way and The Walk" is a static website for a father-son spiritual development program. It presents a year-long curriculum with monthly themes, scripture study, and activities. The site is hosted on GitHub Pages at wayandwalk.org (configured via `CNAME`).

## Development

No build system, dependencies, or tooling required. To preview locally:

```bash
python3 -m http.server 8000
```

## Architecture

The entire application lives in a single file: `index.html`. It contains embedded CSS (`<style>`), embedded JavaScript, and all HTML markup.

**CSS** uses CSS custom properties defined in `:root` for the color palette (stone, earth, warm-cream, parchment, gold, sage, rust) and responsive typography via `clamp()`.

**JavaScript** is vanilla ES6+ with a central data structure containing the full 12-month curriculum. Each month entry has:
- `theme` — monthly title
- `scripture` — primary scripture reference
- `fatherAssignment` / `sonAssignment` — role-specific tasks
- `discussion` — conversation guide questions
- `theWalk` — practical action items

The JS renders curriculum content dynamically when a user selects a month tab. It also handles navigation highlighting and the mobile hamburger menu.

**Sections** (in document order): Navigation → Hero → About/Vision → Schedule/Commitment → Resources → Monthly Curriculum
