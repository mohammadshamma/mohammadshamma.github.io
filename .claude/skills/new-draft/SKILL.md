---
name: new-draft
description: Create a new blog post draft file under notes/drafts/ in this Hugo repo. Use when the user wants to start, scaffold, or begin drafting a new blog post, article, or write-up that should stay private (not published) for now — e.g. "start a draft about X", "new draft", "begin writing a post on Y".
---

# Create a new blog post draft

Scaffold a new draft Markdown file under `notes/drafts/`. Hugo never builds anything under `notes/`, so drafts stay private to the repo until they're promoted into `content/posts/`.

## Steps

1. Determine the draft **title** from the user's request. If no title/topic is given, ask for one before creating the file.
2. Derive a **slug** by lowercasing the title, replacing spaces and punctuation with hyphens, and collapsing repeats (e.g. "My First Post!" → `my-first-post`).
3. Choose the file path `notes/drafts/<slug>.md`. If a file with that name already exists, ask the user whether to pick a different name rather than overwriting.
4. Get today's date in `YYYY-MM-DD` form (run `date +%F`) for the front matter.
5. Write the file using the template below, filling in the date and title.
6. Confirm the created path to the user and offer to start outlining or drafting the body.

## Template

```markdown
+++
date = '<YYYY-MM-DD>'
draft = true
title = '<Title>'
+++

<!-- Draft. Lives in notes/drafts/ and is NOT published.
     When ready: move to content/posts/<slug>.md and set draft = false. -->

## Introduction

TODO
```

## Notes

- Use TOML front matter (`+++`) to match `archetypes/default.md`, so the draft can be moved straight into `content/posts/` later.
- Keep `draft = true` and the file under `notes/drafts/` — do NOT create it in `content/`.
- One file per draft; never overwrite an existing draft without confirmation.
