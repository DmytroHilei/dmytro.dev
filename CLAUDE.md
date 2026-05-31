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
- `src/components/` — reusable `.astro` components imported into pages
- `public/` — static assets served as-is (favicons, etc.)
- `src/assets/` — assets processed by Astro's image pipeline (imported in `.astro` files)

Currently the site is the default Astro scaffold. The `Welcome.astro` component and its associated assets (`astro.svg`, `background.svg`) should be replaced when building out the real portfolio.

## Design direction

Aesthetic target: **karpathy.ai** — minimal, text-first, no hero animations, feels handbuilt not templated.

- Dark or near-white theme (not gray-gradient)
- Typography does the work; no decorative elements
- No card grids, no badge pills, no section headers like "My Projects"
- Projects listed as clean lines with brief descriptions and links
- No animations or transitions beyond the essential

All content (bio, projects, awards, links) is in `CONTEXT.md`.
