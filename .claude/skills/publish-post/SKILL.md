---
name: publish-post
description: Publish a blog post draft from notes/drafts/ — move it into content/posts/, preview it on the local Hugo dev server so the user can review and fix issues, then finalize it (draft = false) and run a production build. Use when the user wants to publish, ship, go live with, or release a draft post — e.g. "publish my draft", "ship the post about X", "make this draft live".
---

# Publish a blog post

Takes a draft from `notes/drafts/` (which Hugo never builds) into `content/posts/` (the published section — `mainSections = ['posts']` in `hugo.toml`), gives the user a live preview to fix issues, then finalizes and verifies a clean production build.

**This is a two-checkpoint flow. Never set `draft = false` or build for production until the user has previewed and approved.** Publishing publicly happens only when the user later pushes to `master` (CI deploys) — this skill prepares the post and stops before pushing unless explicitly asked.

## Prerequisites

- Use the **extended** Hugo build (required for the SCSS). If `hugo version` doesn't show "extended", tell the user and stop.
- Work from the repo root.

## Phase 1 — Stage the draft and start a preview

1. **Pick the draft.** Identify the file in `notes/drafts/` the user means. If unclear, list the `.md` files there and ask which one. Confirm the file exists.
2. **Sanity-check the content.** Read the draft. Warn (don't block) if the body is still placeholder/`TODO` or the title looks like a default. Confirm there's a `title` in the front matter.
3. **Choose the destination.** `content/posts/<slug>.md`, where `<slug>` is the draft's filename (keep the existing slug unless the user wants a different one). Create `content/posts/` if it doesn't exist. If a post with that name already exists, ask before overwriting.
4. **Move the file** (move, don't copy) from `notes/drafts/<slug>.md` to `content/posts/<slug>.md`. Use `git mv` if the repo is git-tracked, otherwise `mv`.
5. **Keep `draft = true` for now.** Leave the front matter as a draft during preview so an accidental production build won't expose it yet.
6. **Start the dev server in the background**: run `hugo server -D` (the `-D` renders drafts). Use a background process so it keeps running while the user reviews.
7. **Point the user to the preview.** Give them `http://localhost:1313/` and, when you can derive it, the direct post URL (typically `http://localhost:1313/posts/<slug>/`). Ask them to review and tell you about any fixes — or say it looks good.

## Phase 2 — Iterate on fixes

- Apply any edits the user requests directly to `content/posts/<slug>.md`. The running `hugo server` live-reloads, so they can re-check immediately.
- Stay in this phase until the user confirms the post is ready to go live.

## Phase 3 — Finalize (only after explicit user approval)

1. In `content/posts/<slug>.md` front matter, set **`draft = false`** and set **`date`** to today (`date +%F`) unless the user wants to preserve the original date.
2. Stop the background `hugo server` process.
3. Run a production build to verify it compiles cleanly: `hugo --gc --minify`. Report success or surface any errors/warnings.
4. Summarize what's ready: the new file path and that the post is now a non-draft. Remind the user that the post goes **publicly live only when `master` is pushed** (CI in `.github/workflows/hugo.yml` deploys to GitHub Pages).
5. **Do not commit or push unless the user asks.** If they do, follow the repo convention: branch rather than committing directly to `master`.

## Notes

- Match existing front matter style: TOML (`+++`), keys `date`, `draft`, `title` (see `archetypes/default.md`).
- Don't touch files under `themes/` (submodule). Don't leave a stray copy of the draft in `notes/drafts/` after moving.
- If the user aborts during preview, you can move the file back to `notes/drafts/` and stop the server so nothing is left half-published.
