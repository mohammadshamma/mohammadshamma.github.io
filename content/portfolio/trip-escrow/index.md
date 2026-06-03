---
title: "Trip Escrow"
date: 2026-01-01
weight: 20
description: "A smart escrow for couples planning a surprise trip — neither reveals their destination."
platform: "Web app"
tech: ["AI escrow agent", "Surprise trips", "LLM-built", "Gemini", "Cloud Run", "Firebase"]
externalUrl: "https://trip-escrow.negfeed.com"
externalLabel: "Visit site"
# image: "cover.png"   # optional — drop cover.png in this folder to enable
---

The idea came from my longtime manager at Google Wallet, who mentioned that he and
his boyfriend liked to surprise each other by secretly planning trips to different
places. I loved it, and wanted to do the same with my wife: our birthdays are about
two months apart, so we could each plan a getaway for the other — with one rule,
that we don't both pick the same destination.

Trip Escrow is the neutral middle that makes that work. One partner secretly locks
in a destination — Gemini validates that it's a real, unambiguous place — while the
other submits three options of their own. The app then uses Gemini to choose the
option most geographically distinct from the hidden pick, so you both end up
somewhere genuinely new, with the surprise intact until the reveal. Once a choice is
made the session locks, so no one can peek or change their answer.

The concept started as a prototype in Google AI Studio. From there I used Claude to
rework the code to run on Google Cloud Run, with Firebase as the database. The front
end is React with an Express API, and Gemini handles both the location validation
and the final selection.

More than the trip planning, I think the underlying pattern is the interesting part:
using an LLM as a trusted escrow agent — something that holds a secret and acts on
it fairly without leaking it to either side. As agents grow more secure and more
trusted, I expect that opportunity to keep growing.
