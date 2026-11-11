---
title: '{{ replace .File.ContentBaseName "-" " " | title }}'
date: '{{ .Date }}'
draft: true
description: ""
platform: "Interactive artifact"
tech: []
cardCta: "Open artifact"
image: "preview.png"   # capture at 1200x630 (1.91:1) in this folder; powers /artifacts/ card & social unfurls
imageAlt: ""
# imageAnchor: "Center" # optional crop anchor ("Top", "Center", "Bottom", "Smart") or use socialImage for a separate file
# Place the self-contained HTML file at assets/artifacts/<slug>/index.html
# Must dynamically adapt to viewport width & height (__applyHostViewport / 100dvh) — see AGENTS.md
---
