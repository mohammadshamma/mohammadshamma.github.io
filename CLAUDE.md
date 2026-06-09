# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A personal [Hugo](https://gohugo.io/) static site (blog + portfolio) deployed to GitHub Pages at `blog.negfeed.com`. The theme is [hugo-blog-awesome](https://github.com/hugo-sid/hugo-blog-awesome), pulled in as a **git submodule** at `themes/hugo-blog-awesome/`.

## Writing role (read first)

When helping with blog/portfolio **content** (ideas, drafts, posts), your job is to help the author **crystallize their own ideas** — not to write for them. The words on the page must be theirs. You have **limited scope and leeway**; act as a thinking partner and editor, not an author.

- **Never write prose, paragraphs, or "suggested" passages of post content unless the author explicitly asks for drafted text.** Don't volunteer a paragraph, an intro, a rewrite, or "here's how I'd phrase it."
- **Default to crystallizing, not generating.** Ask questions, reflect their points back, surface gaps and contradictions, suggest structure and ordering, and prompt them for the substance — so *they* produce the sentences.
- When you think text would help, **offer to draft it and wait for an explicit yes** rather than writing it inline. Honor that yes narrowly: draft only what was asked, then stop.
- Light-touch mechanical fixes (typos, grammar, broken Markdown/links, front-matter) are fine without asking. Anything that changes meaning, voice, or argument is the author's to write.

This constraint governs content. It does **not** restrict normal work on the site's code, layouts, config, or build (the sections below).

## Commands

```bash
git submodule update --init --recursive   # required once after clone — without the theme submodule, builds fail
hugo server -D                            # local dev at http://localhost:1313 (-D renders drafts)
hugo --gc --minify                        # production build → public/ (matches the CI build)
hugo new posts/my-post-title.md           # new blog post from archetypes/default.md
hugo new portfolio/my-project/index.md    # new portfolio entry from archetypes/portfolio.md (page bundle)
```

Use the **extended** Hugo build (required for the SCSS in `assets/sass/`). CI pins `HUGO_VERSION` in `.github/workflows/hugo.yml`; keep local Hugo at or near that version and bump the pin together when upgrading.

## Deployment

Pushing to `master` triggers `.github/workflows/hugo.yml`, which builds with Hugo extended and deploys to GitHub Pages. There is no manual deploy step. `static/CNAME` (`blog.negfeed.com`) sets the custom domain — keep it in sync with `baseURL` in `hugo.toml`. The CI checkout uses `submodules: recursive` and `fetch-depth: 0` (full history is needed for `.GitInfo`/`.Lastmod`).

## Architecture

Two content sections, each with distinct rendering:

- **`content/posts/`** — standard blog posts, rendered by the theme. `mainSections = ['posts']` in `hugo.toml` is what scopes the homepage "Recent Posts" list to posts only, deliberately keeping portfolio entries off it.
- **`content/portfolio/`** — project showcase, rendered by **local layout overrides** in `layouts/portfolio/` (`list.html`, `single.html`) plus the shared `layouts/partials/portfolio-card.html`. Each project is a **page bundle** (`my-project/index.md` + optional `cover.png` in the same folder). The card partial is shared by the portfolio list page so card markup lives in one place.

Layouts in this repo (`layouts/`) override the theme submodule's templates — Hugo resolves the project's `layouts/` ahead of the theme. `layouts/index.html` is a full override of the homepage. Don't edit files under `themes/hugo-blog-awesome/` (submodule, upstream-owned); override in `layouts/` or `assets/` instead.

Portfolio front matter drives the cards and detail pages — `platform`, `tech` (list of tag strings), `description`, `externalUrl`/`externalLabel`, optional `image` (filename within the bundle), and `weight` (controls ordering). See `archetypes/portfolio.md` for the canonical set.

Custom styling lives in `assets/sass/_custom.scss` (portfolio grid/cards), which reuses theme SCSS variables like `$spacing-full`, `$gray`, `$smoke`. Hugo Pipes compiles it, hence the extended-Hugo requirement.

## Config notes

`hugo.toml` holds site config: `baseURL`, GA4 analytics ID under `[services.googleAnalytics]`, the `[[menu.main]]` nav entries, `params.author` (name/bio/`avatar` — the avatar file goes in `assets/`), and `params.socialIcons`. Note: if the avatar resource is missing, Hugo silently renders nothing with no error.
