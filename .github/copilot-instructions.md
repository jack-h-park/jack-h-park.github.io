<!-- .github/copilot-instructions.md -->
# Guidance for AI coding agents working on this repository

This repository is a small personal Jekyll site (GitHub Pages compatible). The goal of these instructions is to give an AI coding agent the essential context to be immediately productive.

Key facts
- Project type: Jekyll static site using the `minima` theme. See `Gemfile` for plugin and theme versions (uses `github-pages` group).
- Primary content: Markdown posts live in `_posts/`. Site configuration lives in `_config.yml`. Built site output is generated into `_site/`.

Build & dev workflow
- Install/update Ruby gems with `bundle install` (uses `Gemfile`).
- Run locally and auto-regenerate with: `bundle exec jekyll serve`.
- When changing `_config.yml`, restart the dev server (Jekyll doesn't reload that file automatically).

Conventions & patterns to follow
- Posts: filenames in `_posts/` must follow `YYYY-MM-DD-title.MARKUP` and include YAML front-matter (see `_posts/2025-10-02-welcome-to-jekyll.markdown`).
- Theme: site uses `minima`; changes to layouts/content should be conservative — prefer editing site files (like `index.markdown`, `about.markdown`) rather than overriding theme internals unless necessary.
- Static assets and output: generated files appear under `_site/` — do not edit generated files directly.

Files to inspect for changes
- `_config.yml` — site-wide settings (title, email, description, baseurl, url, plugins). Changing this requires restarting the server.
- `Gemfile` — controls Jekyll and plugin versions. Use `bundle install` / `bundle update` to manage.
- `_posts/` — source content for blog posts. Edit or add posts here.
- `index.markdown`, `about.markdown` — main pages.

Examples of typical tasks and how to approach them
- Add a new post: create a file in `_posts/` with the proper filename and front-matter, then run the server to preview.
- Update site metadata: edit `_config.yml`, restart `bundle exec jekyll serve`, and verify changes at `http://127.0.0.1:4000`.
- Add a plugin or theme change: update `Gemfile`, run `bundle install`, and test locally.

Integration points & external dependencies
- GitHub Pages: repository is sized for GitHub Pages; if enabling Pages builds, prefer the `github-pages` gem (already present in `Gemfile`).
- No external APIs or services referenced in source; treat this repo as a pure static site generator project.

Editing and PR guidance
- Edit source files (Markdown, `_config.yml`, Gemfile). Don't modify `_site/` — it's generated.
- Keep commits small and focused: content changes vs configuration vs dependency updates.

What not to do
- Don't attempt to run or modify server-side services — this is a static site.
- Avoid changing theme internals in-place. If layout changes are required, add overrides in the repository and test locally.

Quick checklist for agents before committing
1. Run `bundle install` if `Gemfile` changed.
2. Run `bundle exec jekyll build` or `bundle exec jekyll serve` and confirm site builds without errors.
3. Verify content changes are present in `_site/` output (only for smoke-checking; do not commit generated files).

If something is unclear
- Ask the repo owner for preferred publishing steps (GitHub Pages settings) or any non-default workflow.

Files referenced: `_config.yml`, `Gemfile`, `_posts/2025-10-02-welcome-to-jekyll.markdown`, `index.markdown`, `about.markdown`.

Please ask for clarification if you need workflow details (local Ruby version, bundler version, or Pages settings).
