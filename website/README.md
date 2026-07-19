# KAI Scheduler documentation website

This directory builds the KAI Scheduler documentation website with
[Hugo](https://gohugo.io/) and the [Docsy](https://www.docsy.dev/) theme.

The site content is **not** duplicated here — the pages under the repo-root
[`../docs`](../docs) directory are mounted into the site (see the `module.mounts`
section of [`hugo.toml`](hugo.toml)), so the same Markdown renders on GitHub and
on the website. Only site scaffolding (homepage, config, theme wiring) lives here.

## Prerequisites

- [Hugo **extended**](https://gohugo.io/installation/) ≥ 0.110.0
- [Go](https://go.dev/) ≥ 1.23 (Docsy is pulled in as a Hugo Module)
- [Node.js](https://nodejs.org/) ≥ 18 (PostCSS/autoprefixer for the CSS pipeline)

## Local development

```bash
cd website
npm install            # PostCSS toolchain
hugo mod get           # fetch the Docsy module
hugo server            # serve at http://localhost:1313/KAI-Scheduler/
```

## Production build

```bash
cd website
npm install
hugo mod get
hugo --minify --baseURL "https://<owner>.github.io/KAI-Scheduler/"
# output in website/public/
```

## Deployment

Pushing to `main` (touching `docs/**` or `website/**`) triggers
[`.github/workflows/deploy-docs.yaml`](../.github/workflows/deploy-docs.yaml),
which builds the site and publishes `website/public/` to the `gh-pages` branch.

### One-time repository setup

In **Settings → Pages**, set **Source: Deploy from a branch**, **Branch:
`gh-pages` / `(root)`**. The site is then served at
`https://<owner>.github.io/KAI-Scheduler/`.

## Notes

- Content lives in `../docs`; edit those files, not copies here.
- Cross-links between docs pages (`../queues/_index.md`, `foo.md#anchor`, …) are
  resolved to site URLs by Docsy's built-in link render hook, so the same
  Markdown works on GitHub and on the site.
- A few docs link to repo **source files** outside `docs/` (e.g. `examples/`,
  `cmd/.../options.go`). Those resolve on GitHub but 404 on the site — readers
  reach them via the navbar GitHub link. Converting them to absolute GitHub URLs
  is a possible follow-up.
- "Edit this page" links are intentionally disabled because content is mounted
  (Docsy cannot compute a correct source path through a mount).
- The `../docs/scale-tests/` dashboard app is excluded from the mount.
- Design docs under `../docs/developer/designs/` use `README.md` (not `_index.md`)
  and render as regular pages; converting them to section indexes is a possible
  follow-up.
