+++
date = '2026-06-09'
draft = true
title = 'Engineers and Users Drowning in a Sea of Skills'
+++

<!-- Draft. Lives in notes/drafts/ and is NOT published.
     When ready: move to content/posts/engineers-and-users-drowning-in-a-sea-of-skills.md and set draft = false. -->

## Introduction

- Engineers and users are drowning in a sea of skills.
- The problem isn't bad actors — it's abundance with no way to tell skills apart.
- TODO: open on the felt experience of overload (the moment of facing N options and not knowing which to pick).

## Proliferation

- How many skills are available in public skill marketplaces today — the size of the sea.
- TODO: real numbers + named source(s); verify before citing (these stats are themselves often unsourced).

## Overlap (the texture of the sea)

- The real symptom: tens or hundreds of skills that do the same thing.
- Dividing line: honest variation (same problem solved differently/better) vs. redundant noise — without assuming bad intent.
- TODO: evidence — count overlapping skills in a few categories (commit messages, PR review, changelog).

## Scarce context

- My agent context has limited space and a cap on how many skills it can use — and so does yours.
- You can only keep a few above water: many skills, little room.
- TODO: decide voice — "my agent" (a person) vs. written as an agent addressing the reader.

## The structural incentive

- The ecosystem rewards visibility, not verified impact.
- A good-faith author surfacing their work and a low-effort clone look identical from the outside.

## Which skills should I pick?

- What metric should I trust? Expertise of the author? Stars or likes left on the skill?

## Why those signals fail

- These measures can be manipulated and/or simply do not reflect the true quality of a skill file — even when no one is gaming them.

## What actually reflects quality

- How often a skill was fetched by an agent AND put the session on a good trajectory, based on the user's opinion.
- TODO: resolve framing — raw fetch count is itself a vanity metric. The real signal is outcome-conditioned: given it was fetched, did the trajectory improve?

## Why measuring this is hard

- A skill is one input among many: model in use, context constructed by the user, prompt used, steering decisions.
- Lack of tools to evaluate the performance of mainstream agentic applications — a user can't revisit sessions to mark them and evaluate agent performance.

## Opportunities found in problems

- Implement agentic evaluation tooling that allows evaluating agent performance.
- Estimate skill impact as part of these evaluating agents.
- Double down on past evaluation results to evaluate edits to skills.
