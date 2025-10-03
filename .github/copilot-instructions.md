<!-- .github/copilot-instructions.md -->

# Guidance for AI coding agents working on this repository

This repository is a small personal Jekyll site (GitHub Pages compatible). The goal of these instructions is to give an AI coding agent the essential context to be immediately productive.

Key facts

- Project type: Jekyll static site using the `minima` theme. See `Gemfile` for plugin and theme versions (uses `github-pages` group).
- Primary content: Markdown posts live in `_posts/`. Site configuration lives in `_config.yml`. Built site output is generated into `_site/`.

<!-- .github/copilot-instructions.md -->

# Quick guidance for AI coding agents

This repository is a personal Jekyll site (GitHub Pages). The instructions below contain repository-specific facts and examples an AI agent should use when authoring changes.

- Project: Jekyll static site. Source content: `_posts/`, `index.markdown`, `about.markdown`. Generated output: `_site/` (do not edit).
- Theme/plugins: See `Gemfile` and `_config.yml`. This repo uses `remote_theme: "mmistakes/minimal-mistakes@4.27.3"` (note the remote theme) and the `github-pages` + `jekyll-include-cache` gems.

Important workflows

- Install deps: run `bundle install` (use `bundle exec` when running Jekyll).
- Serve locally: `bundle exec jekyll serve` → preview at http://127.0.0.1:4000. Restart the server after editing `_config.yml`.
- Build for verification: `bundle exec jekyll build`. Do not commit files under `_site/`.

Conventions you must follow

- Posts: add/edit files in `_posts/` using the `YYYY-MM-DD-title.MARKUP` filename and include YAML front-matter. Example: `_posts/2025-10-02-welcome-to-jekyll.markdown`.
- Config: global settings live in `_config.yml`. Changes here require a server restart to take effect.
- Theme changes: prefer adding overrides in the repo (create `_layouts/` or `_includes/` only when needed). Avoid editing theme internals upstream.

Typical tasks (how to approach)

- Add a new post: create `_posts/YYYY-MM-DD-slug.md` with front-matter, run the local server, and confirm the new post appears.
- Update metadata: edit `_config.yml`, restart `bundle exec jekyll serve`, and check the rendered site.
- Add a plugin or upgrade theme: update `Gemfile`, run `bundle install`, then `bundle exec jekyll build` to validate.

Repository-specific notes and gotchas

- Remote theme: `_config.yml` sets `remote_theme: "mmistakes/minimal-mistakes@4.27.3"`. Be aware of differences between the remote theme version and local `minima` gem—overrides may be necessary.
- The `Gemfile` includes `github-pages` in `:jekyll_plugins` group and `jekyll-include-cache`; prefer testing any dependency change locally with `bundle exec jekyll build`.
- `_site/` is generated and checked into the repo for this site. Do not modify generated files directly; update source and rebuild.

Files to inspect when making changes

- `_config.yml` — global settings and remote theme reference.
- `Gemfile` — plugins and gem groups.
- `_posts/` — content source.
- `index.markdown`, `about.markdown` — top-level pages.

Quick pre-commit checklist

1. If you changed `Gemfile` or `_config.yml`, run `bundle install` and `bundle exec jekyll build` locally.
2. Confirm the site builds with no errors and the intended changes appear under `_site/` (for verification only).
3. Do not commit changes inside `_site/` unless explicitly asked (this repo includes `_site/` but prefer committing source edits).

If anything is unclear, ask the repo owner about preferred Ruby/bundler versions or GitHub Pages publishing settings.

References: `_config.yml`, `Gemfile`, `_posts/`, `index.markdown`, `about.markdown`
