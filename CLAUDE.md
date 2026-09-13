# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Personal portfolio site for Dmytro Hilei — an ML/HPC engineering student at TalTech. Built with Astro 6, targeting static output. The source of truth for all portfolio content (bio, projects, links, design intent) is `CONTEXT.md` — read it before making any content or layout decisions.

## Commands

```sh
npm install        # install dependencies (Node >= 22.12.0)
npm run dev        # dev server at localhost:4321
npm run build      # build to ./dist/
npm run preview    # preview the production build locally
npx astro check    # TypeScript type-check .astro files
```

There is no test suite or lint config yet.

## Architecture

Standard Astro file-based routing:

- `src/pages/` — each `.astro` file becomes a route; `index.astro` is the homepage
- `src/layouts/` — `Layout.astro` wraps pages with the HTML shell (head, meta, global styles)
- `public/` — static assets served as-is (favicons, etc.)

The site is a single page: `src/pages/index.astro` holds all the markup and its scoped styles, `src/layouts/Layout.astro` holds the HTML shell and global styles. There are no components yet — add `src/components/` only if a real second page appears.

## Design direction

The page reads as a **document, close to `CV.pdf`** — minimal, text-first, feels handbuilt not templated.

- Near-white theme; typography does the work, no decorative elements
- Section headings with a hairline rule; entry titles bold on the left, date or stack right-aligned in mono
- Tight `·` bullet lists under each entry, mirroring the CV
- No card grids, no badge pills, no hero, no animations
- Every factual claim that can be sourced links to its source (medals → official results, PRs → GitHub)

All content (bio, projects, awards, links) is in `CONTEXT.md`, which mirrors `CV.pdf`.
