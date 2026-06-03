---
title: "Vocalize"
date: 2026-01-01
weight: 10
description: "A voice-first journal that transcribes what you say and distills it into daily and monthly AI summaries."
platform: "Web app"
tech: ["Voice journaling", "AI summaries", "LLM-built", "Replit", "Cloud Run", "Firebase", "Vertex AI"]
externalUrl: "https://vocalize.negfeed.com"
externalLabel: "Visit site"
# image: "cover.png"   # optional — drop cover.png in this folder to enable
---

Vocalize is a diary I'd dreamed about for years — and one I could only build now.
The idea was always the same: a journal you simply *talk* to, that quietly makes
sense of what you said over time. For a long time it stayed a daydream, blocked on
two hard problems. LLMs cleared both. They let me prototype and build the app far
faster than I ever could have alone, and they finally made the core feature
possible — turning rambling, spoken entries into summaries worth reading.

So that's what it does. Speak freely and it captures your voice notes, transcribes
them with Google Cloud Speech-to-Text, and uses Vertex AI to distill the day into a
clean summary — then rolls those up into monthly summaries so you can look back
across weeks at a glance. You can also open a chat and ask questions across
everything you've recorded.

I built the first version on Replit and had something working end to end —
recording, transcription, and summaries — in under four hours. Once it was real,
the catch was cost: Replit hosting added up quickly. So I had Claude Opus rework
the code to run on Google Cloud Run instead, which dropped the hosting bill
dramatically while keeping the same Express backend, Firebase database, and Vertex
AI summarization.
