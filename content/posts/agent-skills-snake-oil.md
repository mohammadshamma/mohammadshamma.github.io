+++
date = '2026-06-08'
draft = true
title = 'Agent Skills Are the New Snake Oil'
tags = ['ai', 'agents', 'skills', 'opinion']
+++

Walk into any AI corner of the internet this month and you'll trip over a
"skill." A markdown file, a clever prompt, a folder with a `SKILL.md` and a
confident README. Each one promises to make your agent smarter, faster, more
*agentic*. Each author is sure theirs is the one that matters.

I've started to recognize the cadence. It's the cadence of the patent-medicine
wagon rolling into town.

## The pitch is always the same

The 19th-century snake oil salesman didn't sell you a chemical. He sold you a
*story*: a testimonial, a confident posture, a crowd that nodded along. The
bottle's contents were almost beside the point. What he was really selling was
the feeling that you'd be left behind if you didn't buy in.

Swap the wagon for a GitHub repo and the tonic for a prompt template, and the
script reads identically. "This skill made my agent 10x better." Better at
what? Measured how? Against what baseline? The pitch evaporates the moment you
ask, because the pitch was never built to survive the question.

## No evaluations, no accountability

Here's the part that should bother us more than it does: almost none of these
skills come with evidence.

- No held-out evaluation set.
- No before/after numbers on a task anyone else can run.
- No record of how often the skill *hurt* — because of course it sometimes
  does, and nobody's measuring.
- No way to attribute a good outcome to the skill versus the model getting
  better underneath it, the prompt, the phase of the moon.

A skill ships, a thread goes viral, a star count climbs. The outcome — the
thing the skill supposedly improves — is never inspected. We've recreated the
testimonial economy with better syntax highlighting. "Works on my machine"
became "worked on my agent, once, probably, vibes."

If a pharmaceutical company shipped a pill with the evidentiary rigor of the
median agent skill, we'd call it fraud. In our corner of software we call it
a Tuesday and ask the author to do a conference talk.

## Clout is the actual product

Be honest about the incentive gradient. Authoring a skill is cheap. Measuring
one is expensive. Claiming impact is free and pays in followers.

So the equilibrium we've landed in is the one you'd predict: a flood of
skills, each wrapped in impact language — "supercharge," "unlock," "10x" —
and a near-total absence of the boring instrumentation that would tell you
whether any of it is true. The reward isn't a better outcome for the user.
The reward is attention for the author. The skill is the costume; clout is
the body wearing it.

None of this requires bad faith. The snake oil salesman often believed his
own pitch — that's what made him persuasive. An author who genuinely *felt*
their agent got better, and posted about it sincerely, is indistinguishable
from a grifter precisely because neither of them measured anything. Sincerity
is not evidence.

## What I'd want before I trust a skill

I'm not anti-skill. Reusable, shareable agent capabilities are a genuinely
good idea. I'm anti-*unfalsifiable*. The fix isn't complicated, it's just
unglamorous:

1. **An eval anyone can run.** A task set, a scoring rule, a number. Even a
   small one. Especially a small one.
2. **A baseline.** The same agent, same task, without the skill. If you can't
   show the delta, you haven't shown anything.
3. **The failure cases.** Where does it make things *worse*? A skill with no
   reported failure modes hasn't been used hard enough to trust.
4. **Versioned against a model.** "Improves Claude on X as of date Y." Skills
   decay as models improve; some get actively counterproductive.

That's it. That's the whole bar. It's low. The striking thing is how few
clear it.

## The town after the wagon leaves

Snake oil didn't end because buyers got smarter. It ended because we built
institutions — measurement, labeling, accountability — that made the claims
checkable. The tonic that survived contact with a controlled trial became
medicine. The rest became a cautionary museum exhibit.

Agent skills will go the same way, eventually. The ones with evals will become
infrastructure. The rest will become a folder of `SKILL.md` files nobody
remembers installing, quietly making outcomes worse while their authors have
moved on to the next viral artifact.

Until the measurement shows up, treat the confident pitch for exactly what it
is: a man on a wagon, telling you a story about a bottle, hoping you'll buy
before you think to ask what's actually inside.
