---
title: ERGminer
description: Mining event relationship graphs from event logs
importance: 1
category: research
related_publications:
  - eyde2026ergminer
---

Event relationship graphs (ERGs) are a compact way to represent discrete-event simulation models. Events are the nodes, and the edges say how one event schedules or cancels another. Building them by hand takes time and expertise.

ERGminer is an open-source Python tool that discovers ERG models directly from minimal event logs. Its pipeline combines Alpha Miner process discovery, queueing-network activity classification, system identification, guard detection, and distribution fitting, and outputs an executable ERG that is validated by playback-based conformance testing.

To be presented at the 2026 Winter Simulation Conference in Glasgow, Scotland.
