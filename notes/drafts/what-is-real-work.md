+++
date = '2026-06-07'
draft = true
title = 'What Is "Real Work," Actually?'
+++

<!-- Draft. Lives in notes/drafts/ and is NOT published.
     When ready: move to content/posts/what-is-real-work.md and set draft = false. -->

Picture two people watching the same engineer work through the same day.

The first observer sees the hands. Keys clatter. Code scrolls up the screen.
Files open, fill with lines, and close. Functions appear; tests turn green. By
this account it was a productive day — you could measure it in commits, in
lines, in the sheer sustained motion of someone clearly *working*.

The second observer never looks at the keyboard. They watch the decisions.
They see the engineer reject the obvious approach in the first ten minutes
because it would have coupled two systems that need to stay independent. They
see the moment a single question — *what happens when this runs twice?* — quietly
kills an entire design and forces a better one. They see the trade picked, the
trade refused, the constraint noticed early enough to matter. By this account
the day's real output was a handful of decisions, and the typing was just the
exhaust.

Same engineer. Same day. Same chair. Now: which observer watched the real work?

Most of us, if we're honest, were trained to trust the first observer. Effort
you can see *feels* like the work. But the second observer is the one watching
the thing that was actually hard to do and actually expensive to get wrong. The
code was the easy part. It was always the easy part. We just had a hard time
seeing past the part that moved.

## The gap was always there

Here is the part we don't like to admit: this gap between "looks like work" and
"is valuable" is not new. AI didn't create it.

Steering was always the senior skill. The best architects I've ever worked with
produced the least visible output. They wrote less code than the people they
made more effective. Their fingerprints were on everything and showed up in
nothing you could `git blame`. If you measured them by keystrokes, they looked
like they were coasting. If you measured the systems around them, they were the
reason those systems held together.

We just didn't have to *look* at the gap, because the median engineer still
spent most of the day typing. The visible-effort proxy was wrong at the top of
the org, but it was close enough in the middle that nobody had to confront it.

[TODO: connect to the identity-rupture post — when I became a TL, I lived
inside this gap and it nearly broke me. The crisis of "I'm not writing code
anymore, so what am I even doing" predates LLMs entirely. Cross-link once that
post is up.]

## AI didn't move the line — it turned on the lights

What changed is that AI made the cheap, visible part of the work nearly free.

[TODO: the design-doc example. Brutal deadline — four weeks, one lost to
vacation, a Google I/O launch. The bottleneck was never the code; it was the
*alignment*. I used an agentic tool to produce a polished, diagram-heavy design
doc in two days. That document — not the code — is what shipped the project.
"I used AI to write the document, not the code, and that's why we shipped."
Keep this tight; the full case study is its own post.]

[TODO: the Gemini CLI refactor as a second beat — a single high-level comment
drove a fast, sweeping abstraction. The thinking was the input; the
implementation fell out of it. Decide whether this belongs here or stays in the
"Lego to concrete" post so I don't double-spend the anecdote.]

When typing got cheap, the typing stopped being the work, and what was *left*
was the thing that was always the actual job: deciding what should exist, and
getting people to agree it should exist. AI didn't move the line between busywork
and real work. It just turned the lights on so we could all see where the line
had been the whole time.

## The uncomfortable feeling

I want to name the feeling at the center of this, because I think a lot of
people are sitting in it right now and don't have words for it:

**I did my best work, and it looked like I did nothing.**

That sentence is going to be true for more and more people, more and more often.
The instinct is to manufacture visible effort to feel — and look — productive.
Resist it. The discomfort isn't a sign you're slacking. It's a sign the proxy
you used to measure yourself is finally, mercifully, breaking.

## Conclusion

[TODO: land the plane. Possible close — stop asking "did I look busy today?" and
start asking "what is now true that wasn't true this morning?" The typing was
never the work. It was just the part that was easy to see.]
