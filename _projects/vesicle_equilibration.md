---
layout: page
title: Vesicle Equilibration
description: Hybrid Monte Carlo–MD for equilibrating the leaflet composition of multicomponent vesicles
img: assets/img/projects/vesicle_equilibration_eq2.png
importance: 2
category: membranes
---

Building on the asymmetry found in binary vesicles, I am extending my research to more complex ternary vesicles known to form raft-like domains. Interpreting phase behavior in these systems requires well-defined equilibrium conditions. In molecular dynamics, however, phospholipid flip-flop is far slower than accessible simulation times, so the leaflet composition of a vesicle stays close to the initial guess made when the system is built.

To address this, I am developing a vesicle equilibration methodology based on hybrid Monte Carlo–molecular dynamics (MC-MD). Periodically during MD, Monte Carlo moves swap lipids between the inner and outer leaflets and are accepted or rejected with the Metropolis criterion based on the energy change, allowing the leaflet composition to relax on timescales that plain MD cannot reach. The method is implemented directly in GROMACS 2025, and the code will be released publicly.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/vesicle_equilibration_eq2.png" title="Lipid-swap Monte Carlo move" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Lipid-swap Monte Carlo move. A DPPC and a DIPC in opposite leaflets exchange places, and the swap is accepted with the Metropolis criterion based on the energy change ΔE = E<sub>aft</sub> − E<sub>bef</sub>.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/vesicle_equilibration_eq1.png" title="Inner-leaflet DPPC fraction during equilibration" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Inner-leaflet DPPC fraction X<sub>Inner, DPPC</sub> during equilibration. The pore method converges in about 20 µs, whereas MC-MD converges in about 250 ns, roughly 80 times faster.
</div>
