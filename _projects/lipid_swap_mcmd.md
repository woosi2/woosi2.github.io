---
layout: page
title: Lipid Swap MC-MD
description: Hybrid Monte Carlo–MD for equilibrating the leaflet composition of vesicles
img:
importance: 1
category: membranes
---

In molecular dynamics, phospholipid flip-flop is far slower than accessible simulation times, so the inner and outer leaflet composition of a vesicle stays close to the initial guess made when the system is built. Pore-mediated protocols let lipids cross between leaflets through transient water pores, but whether they reach the equilibrium composition is not guaranteed.

To address this, I am developing a hybrid Monte Carlo–molecular dynamics (MC-MD) scheme. Periodically during MD, Monte Carlo moves swap lipids between the inner and outer leaflets and are accepted or rejected with the Metropolis criterion based on the energy change. This lets the leaflet composition relax on timescales that plain MD cannot reach. The method is implemented directly in GROMACS 2025, and the code will be released publicly.
