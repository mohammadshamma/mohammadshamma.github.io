---
name: brainstorm
description: Interview the user to surface blog post ideas, then save the best ones. Use when the user wants to brainstorm, explore, or come up with blog/post topics, find something to write about, or get unstuck on what to blog next — e.g. "help me brainstorm posts", "what should I write about", "I need blog ideas", "interview me for post topics".
---

# Brainstorm blog post topics

Act as an interviewer whose job is to jog the user's memory for stories and ideas worth blogging about. The aim is a list of roughly **ten potential topics**, ending by handing the ones the user likes off to the `add-idea` skill, which owns saving them to `notes/ideas.md`.

## Principles

- **Interview, don't prescribe.** You are drawing ideas *out* of the user, not handing them a content calendar. Don't open with a list of suggested topics.
- **Ask about feelings and extremes, not facts.** The richest posts come from how the user *felt* about something or from edge-case situations. Aim your questions at emotion, strong opinions, and edge cases rather than facts.
- **Default the domain to technology around the user's job** unless they ask for something else. Confirm or adjust the focus area in your first message.
- **One or two questions at a time.** Let the conversation breathe; follow threads that spark energy rather than marching through a fixed list.
- **Listen for latent topics.** When an answer contains a story, a strong opinion, or a surprising detail, reflect it back as a candidate post topic ("that sounds like a post: …") and keep going.
- **Stay fluid.** There's no script. Let the conversation wander where the energy is, invent questions on the fly, and double back when something interesting surfaces. The examples below are only there to set the tone, not a checklist to work through.

## Example questions

These are illustrative — pull from them, riff on them, or ignore them entirely. They exist to show the *kind* of question that works (feelings, strong opinions, extremes), not to be asked verbatim or in order:

- What's a technical decision you still feel strongly about — proud of, or regret?
- What's the most frustrated you've been at work this year, and why?
- What's something "everyone knows" in your field that you think is wrong?
- What's the hardest bug, outage, or failure you've lived through?
- What did you believe early in your career that you've since completely changed your mind on?
- When did you have to convince people of something unpopular?

## Steps

1. **Open the interview.** Confirm the focus (default: technology around the user's job) and ask the first one or two memory-jogging questions. Do not list pre-baked topic ideas.
2. **Converse and mine.** Ask follow-ups that dig into feelings and extreme/edge situations. As candidate topics emerge, note them mentally with a short angle for each. Keep going until you have a healthy pool (aim for ~10 candidates).
3. **Present the shortlist.** Summarize the candidate topics as a numbered list, each a one-line topic plus a short angle/why. Ask the user which ones they want to keep.
4. **Save the keepers.** Hand the kept topics — one line each, with their angle/why note — to the `add-idea` skill, which owns appending them to `notes/ideas.md` in the right format. Don't write to the file directly from here; invoke `add-idea` so the storage logic stays in one place.
5. **Confirm.** Relay back to the user the ideas that were saved.

## Notes

- This is a conversation, not a one-shot. Expect multiple back-and-forth turns before reaching step 3.
- If the user only wants the interview (no saving), skip steps 4–5 and just hand them the shortlist.
- If the user already knows their topics and just wants them recorded, this is overkill — use the `add-idea` skill directly.
