# AGENTS.md

This repository contains the API documentation for [Space64](https://space64.ai), a visual workflow builder for AI image & video generation.

## Tech stack

- **Mintlify** — docs framework (MDX pages, `docs.json` for config/navigation)
- Content is authored in `.mdx` files at the repo root and in `api-reference/`

## File structure

```
docs.json               — Mintlify config: branding, colors, navigation, navbar
introduction.mdx        — Landing page
quickstart.mdx          — Getting started guide
api-reference/
  introduction.mdx      — API overview (auth, rate limits, errors, credits)
  run-workflow.mdx      — POST /api/v1/workflows/:id/run
  get-run.mdx           — GET /api/v1/runs/:id
logo/                   — Light/dark logo SVGs
images/                 — Hero images
favicon.svg             — Browser favicon
```

## Adding a new page

1. Create a `.mdx` file with frontmatter (`title`, `description`)
2. Add the file path (without extension) to the `navigation` section in `docs.json`
3. Run `npx mint dev` to preview locally

## Source of truth

API implementation lives in the main app repo (`/Users/wayne/Projects/comarketer`):
- Auth: `src/lib/api-auth.ts`
- Run endpoint: `src/app/api/v1/workflows/[id]/run/route.ts`
- Poll endpoint: `src/app/api/v1/runs/[id]/route.ts`
- Rate limiting: `src/lib/rate-limit.ts`
- Credits: `src/lib/credits.ts`
