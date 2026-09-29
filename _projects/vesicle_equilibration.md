---
layout: page
title: Vesicle Equilibration
description: Hybrid Monte Carlo–MD for equilibrating the leaflet composition of multicomponent vesicles
img:
importance: 2
category: membranes
---

Building on the asymmetry found in binary vesicles, I am extending my research to more complex ternary vesicles known to form raft-like domains. Interpreting phase behavior in these systems requires well-defined equilibrium conditions. In molecular dynamics, however, phospholipid flip-flop is far slower than accessible simulation times, so the leaflet composition of a vesicle stays close to the initial guess made when the system is built.

To address this, I am developing a vesicle equilibration methodology based on hybrid Monte Carlo–molecular dynamics (MC-MD). Periodically during MD, Monte Carlo moves swap lipids between the inner and outer leaflets and are accepted or rejected with the Metropolis criterion based on the energy change, allowing the leaflet composition to relax on timescales that plain MD cannot reach. The method is implemented directly in GROMACS 2025, and the code will be released publicly.
