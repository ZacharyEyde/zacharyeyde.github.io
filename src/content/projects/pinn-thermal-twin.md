---
title: Physics-Informed Thermal Twin for Final Test
description: PINNs for detecting thermal-contact defects at the die-to-test-head interface
importance: 3
category: research
---

As chiplet integration drives up thermal complexity, gross contact defects at the die-to-test-head interface (voids, tilt, or dry or missing thermal interface material) can cripple heat transfer while the tester only sees its control thermocouple.

This work builds a physics-informed neural network in NVIDIA PhysicsNeMo as a surrogate model of the test-head-to-die thermal stack. Because the heat-transfer equations and boundary conditions are built into training, its predictions stay physically realistic even for defects never seen in data. The goal is to screen the thermal-contact region during the start-of-test soak, so bad-contact hardware is caught and removed before it enters active test.

Presented at SEMICON West 2026. See the [talks page](/talks/).
