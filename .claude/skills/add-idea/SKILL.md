---
name: add-idea
description: Append a blog post idea to notes/ideas.md in this Hugo repo. Use when the user wants to jot down, capture, save, or log a blog/post idea, topic, or thing to write about for later — e.g. "add an idea", "note down a post idea", "I want to write about X someday".
---

# Add a blog post idea

Append a new idea to `notes/ideas.md` at the repo root. This file is a scratch list that Hugo never builds, so it stays out of the published site.

## Steps

1. Determine the idea text from the user's request. If they didn't give a clear idea, ask them for the one-line idea before writing anything.
2. Read `notes/ideas.md` (create it from the template below if it doesn't exist).
3. Append a new bullet at the end of the file in this format:
   ```
   - [ ] <idea> — <optional one-line note on the angle/why>
   ```
   Keep the idea to a single line. Only include the `— note` part if the user gave context or you can add a genuinely useful angle; otherwise omit it.
4. Confirm to the user what was added and show the new line.

## Notes

- Do NOT create files under `content/` — ideas live only in `notes/ideas.md`.
- Preserve existing content; only append. Never reorder or rewrite other entries.
- If the user gives several ideas at once, add one bullet per idea.

## Template (only if notes/ideas.md is missing)

```markdown
# Blog Post Ideas

A running list of post ideas.

<!-- Format: - [ ] One-line idea — optional note on the angle/why -->
```
