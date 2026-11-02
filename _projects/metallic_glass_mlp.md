---
layout: page
title: Fatigue of Metallic Glasses
description: Machine-learning interatomic potentials for the microscopic mechanism of fatigue
img: assets/img/projects/metallic_glass_3.png
importance: 1
category: materials
---

Metallic glasses combine high strength with the absence of crystalline defects, yet their fatigue limits are low, and the general mechanism behind this remains unclear. Addressing this question requires simulations across a broad range of compositions with accuracy close to first-principles calculations.

To this end, I developed a machine-learning interatomic potential (MLIP) for Zr–Ni–Al metallic glasses trained on DFT data. Using MD simulations of cyclic loading, I am now studying how local atomic structure, such as icosahedral clusters and their networks, relates to atomic rearrangements, to uncover the microscopic mechanisms of fatigue in metallic glasses.

<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/metallic_glass_1.png" title="MTP vs DFT energy" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/metallic_glass_2.png" title="MTP vs DFT force" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Parity plots of the moment tensor potential (MTP) against DFT for energies and forces.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/metallic_glass_5.png" title="Strain-controlled cyclic loading" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Strain-controlled cyclic loading of Zr<sub>7</sub>Ni<sub>3</sub>Al<sub>1</sub> (R = 0.1, ε<sub>max</sub> = 0.02–0.06) over 100 cycles.
</div>

<div class="row">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/metallic_glass_3.png" title="Full icosahedral cluster" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/metallic_glass_4.png" title="Icosahedral cluster network" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: a full icosahedral cluster in the glass. Right: connected network of icosahedral clusters under periodic boundary conditions, and the largest cluster as a fraction of all icosahedra for four compositions (931 = Zr<sub>9</sub>Ni<sub>3</sub>Al<sub>1</sub>, 731 = Zr<sub>7</sub>Ni<sub>3</sub>Al<sub>1</sub>, 933 = Zr<sub>9</sub>Ni<sub>3</sub>Al<sub>3</sub>, 733 = Zr<sub>7</sub>Ni<sub>3</sub>Al<sub>3</sub>).
</div>
