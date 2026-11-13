+++
date = '2026-11-13'
draft = false
title = 'Software as Equilibrium: The Forces That Shape What We Build'
description = "Software isn't designed top-down—it's a temporary equilibrium where competing forces balance out for a share of engineering time."
socialImage = 'social.jpg'
imageAlt = 'Minimalist ink illustration of six silhouettes pulling taut ropes to suspend a cube in equilibrium'
+++

![Minimalist ink illustration of six silhouettes pulling taut ropes to suspend a cube in equilibrium](cover.png)

I've spent more than eleven years on the Google Wallet team. Over that time I've come to believe that software isn't really *designed*, at least not the way we like to tell it. No architect draws the final shape and then the team builds it. What you see at any moment is where a set of competing forces happen to balance out. Software is an equilibrium, and a temporary one.

This post is my attempt to name those forces. It's a framework more than an argument. I want a clear picture of what actually shapes a product, because I'll need it soon to ask a harder question: what happens to all this when agents start writing the code?

## The forces

**Market needs and opportunity.** This is the force that pulls a product forward: new use cases, competitors, openings that may not stay open for long. It's the reason the software changes at all.

**Customer feedback.** People who use the product want it to be better, and they tell you when it gets worse. Feature requests, complaints and regression reports all push the product toward what users actually experience, not what the roadmap assumed.

**User inertia.** This is the quiet opposite of feedback. Once people depend on how something works, changing it costs them something. Existing users resist change even when the change is an improvement, and the older the product, the stronger this force gets.

**Regulation and compliance.** In payments this force is impossible to ignore. Requirements like European compliance work arrive on their own schedule, they don't negotiate, and they have to be done whether or not they fit the plan. Payments aren't unique here. Healthcare, aviation, automotive and other regulated domains feel the same force, often even more strongly.

**Partners.** Banks, card networks and other outside parties have their own systems, timelines and constraints. A wallet only works as well as its integrations, so their limits become your limits.

**Cost and feasibility.** This is the force people usually call "engineering," but I think that's the wrong name. Good engineers don't push back on a whim. They point out what's theoretically impossible, what's expensive, and what will cost more to maintain than it's worth. They're passing along something real: the limits of computation, the cost of complexity, and the steady pull toward entropy that a system has to keep fighting just to stay coherent.

## The channels

The point about engineers applies to every role. Engineers aren't the cost-and-feasibility force; they carry it. Product managers are the same: they carry market needs and opportunity into the room. Every role is a channel for one or more of these forces.

That's where Conway's law fits in. People usually treat it as a fact of life, where your architecture ends up mirroring your org chart. I see it as a tool. Org structure is the lever that VPs and directors control, and it decides how the forces are wired into the organization: which ones get a dedicated team, which ones get a loud voice, and which ones have to fight for attention. Reorganizing doesn't change the forces. It changes how strongly each one gets heard.

Channels aren't perfect. People have their own taste, incentives and pet projects, and those distort the signal. But over years, and as people come and go, that distortion acts as friction rather than as a force. What actually builds up in the product is what lines up with the organization's goals.

## The currency: time

The forces don't push on the code directly. They compete for one limited pool: engineering time.

This is the least controversial claim here, and the most important. Every quarter, compliance work takes time away from product development. Migrations take time away from features. System health takes time away from everything. It's always a trade-off, which is the whole reason coordination exists. If resources were unlimited, there would be nothing to balance.

So the shape of the software at any moment is just what that time bought: how the hours got split among all the forces pulling on it.

## Why software is different

Every industry deals with competing demands and limited budgets. Two things make software unusual.

**It's live.** You don't ship software and walk away. People depend on it working right now, all the time. Keeping it running is a constant demand on the same pool of time.

**It's malleable.** Software is cheap to change compared to physical products, so it goes through far more cycles of evolution. A car model gets redesigned every few years. A software product may change every week. Each cycle is another chance for the forces to shift the balance a little. The tug-of-war never stops; it just happens more often than almost anywhere else.

That's why I call software an equilibrium and not a design. It's always being pulled toward a balance, and the balance keeps moving.

## What comes next

I'm writing this down because I want a yardstick: a way to rethink, from first principles, what software development is in the era of agentic coding. Agents are taking on more of the work, and before deciding what that changes, I want a clear picture of what the work was.

More on that in the next post, when time allows, inshallah.
