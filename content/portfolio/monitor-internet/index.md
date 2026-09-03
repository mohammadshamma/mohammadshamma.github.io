---
title: "Monitor Internet"
date: 2026-08-05
weight: 15
description: "Continuously monitors connection health on macOS and attributes each outage to your equipment, your ISP's line, or upstream transit."
platform: "macOS CLI & daemon"
tech: ["Network monitoring", "ISP accountability", "LLM-built", "Go"]
externalUrl: "https://github.com/mohammadshamma/monitor-internet"
externalLabel: "View on GitHub"
image: "cover.png"
hideCardImage: true
---

Every time my internet acted up, the script with customer support was always the
same: restart the router, check the cables, and assume the fault was inside my own
house. I was dealing with intermittent connectivity drops, and I wanted
indisputable proof before calling to complain or deciding to switch providers. A
simple loop pinging 8.8.8.8 wasn't going to cut it — when ping fails, it can't tell
you whether your Wi-Fi glitched, your router crashed, or the provider's line
actually went down.

To get honest numbers, the tool splits every probe cycle into three distinct
tiers: the local gateway, the ISP's first public edge hop, and independent
internet anchors like Cloudflare, Google, and Quad9. By classifying reachability
across all three tiers simultaneously, it definitively attributes every outage to
LAN equipment, the ISP's physical access line, or upstream transit. It pairs that
with debouncing and backdating to ignore brief noise, while tracking coverage
alongside uptime so machine sleep or reboots never manufacture fake downtime.

The entire Go daemon and CLI was vibe-coded from scratch with Claude Code, and what
amazed me most was that Claude Code made all the core architectural and design
choices itself. Rather than shelling out to the system ping utility and parsing
text output, Claude opted to open unprivileged macOS ICMP datagram sockets directly
in Go — running with zero root or sudo privileges and eliminating process jitter.
It designed the three-tier attribution taxonomy, structured the SQLite WAL
logging, and set up the launchd agents so it runs silently in the background 24/7.
