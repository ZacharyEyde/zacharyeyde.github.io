---
title: Process Digital Twin for Semiconductor Test
description: Modular discrete-event simulation and ML for assembly and test equipment
importance: 2
category: research
related_publications:
  - dodge2025modular
  - eyde2024processdt
---

Digital twins have had far more attention in wafer fabrication than in semiconductor assembly and test, where the barriers are the cost of building and maintaining models, the speed needed for real-time decisions, and the domain expertise required.

This Intel–ASU collaboration builds a process digital twin for test equipment, starting with burn-in. A modular, high-fidelity discrete-event simulation built on SimPy supports offline optimization and analytics, and its output trains machine-learning models (including graph neural networks) that are fast enough to use at runtime. The modular Python library makes it straightforward to assemble digital-twin-ready simulations of new equipment.

Talks: WSC 2024 (poster), SEMICON West 2025, and the 2025 INFORMS Annual Meeting. See the [talks page](/talks/).
