# AGENTS.md

## Repo Shape
- This repo is a plain Jekyll site. There is no committed Node workspace, Gemfile, CI workflow, or task runner.
- Main source locations:
  - `_posts/` for published blog posts
  - `_drafts/` for unpublished drafts
  - `_layouts/` and `_includes/` for shared HTML structure
  - `css/main.scss` as the Sass entrypoint
  - `_sass/` for Sass partials

## Editing Rules
- Do not edit `_site/`; it is generated output and is ignored by Git.
- Keep Sass changes in `css/main.scss` or `_sass/*.scss`. `css/main.scss` is the only Sass file with front matter and imports the partials.
- Site-wide head behavior lives in `_includes/head.html`; changes there affect every page.
- Site navigation is generated from pages with a `title` in front matter via `_includes/header.html`.

## Content And Rendering
- Markdown is rendered with `kramdown` using GFM (`_config.yml`).
- Posts use standard Jekyll post naming and live under `_posts/`.
- MathJax and Kotlin Playground are loaded globally from `_includes/head.html`, so posts can rely on them without per-page setup.
- The custom timeline styling comes from `_sass/_timeline.scss` and is imported by `css/main.scss`.

## Verification
- No repo-local build/test wrappers are committed. Prefer direct Jekyll CLI commands if verification is needed.
- If you change `_config.yml`, restart the Jekyll server; Jekyll does not hot-reload that file.
