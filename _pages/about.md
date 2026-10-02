---
layout: about
title: about
permalink: /
subtitle: Master's Student in Computational Chemistry

profile:
  align: right
  image: prof_pic.jpeg
  image_circular: false
  more_info: >
    <p>Department of Chemistry</p>
    <p>Sogang University</p>
    <p>Seoul, Republic of Korea</p>

selected_papers: true
social: true

announcements:
  enabled: true
  scrollable: true
  limit: 5

latest_posts:
  enabled: false
  scrollable: true
  limit: 3
---

I am a Master's student in the Department of Chemistry at Sogang University.

My research interests lie in **soft matter**, **statistical mechanics**, and **molecular simulation (MD/MC)**. I am particularly interested in understanding the structural and dynamical behavior of complex systems, such as lipid membranes, polymers, electrolytes, and metallic glasses. This is why I am drawn to molecular simulation and fascinated by statistical mechanics, which allow me to explore the microstates of these systems and connect them to macroscopic structural and dynamical properties.

<style>
  .research details {
    margin: 0.6rem 0;
    border: 1px solid var(--global-divider-color);
    border-left: 4px solid var(--global-theme-color);
    border-radius: 6px;
  }
  .research summary {
    position: relative;
    padding: 0.6rem 6rem 0.6rem 0.9rem;
    cursor: pointer;
    list-style: none;
  }
  .research summary::-webkit-details-marker {
    display: none;
  }
  .research summary::before {
    content: "▸";
    display: inline-block;
    margin-right: 0.5rem;
    color: var(--global-theme-color);
    transition: transform 0.2s;
  }
  .research details[open] summary::before {
    transform: rotate(90deg);
  }
  .research summary::after {
    content: "Read more";
    position: absolute;
    top: 0.75rem;
    right: 0.9rem;
    font-size: 0.85em;
    color: var(--global-theme-color);
  }
  .research details[open] summary::after {
    content: "Show less";
  }
  .research summary:hover {
    background-color: var(--global-divider-color);
  }
  .research details > p {
    padding: 0 0.9rem 0.6rem;
    margin: 0;
  }
  @media (min-width: 576px) {
    .post > article > .profile {
      width: 26.25%;
    }
    .post > article > *:not(.profile) {
      margin-right: calc(26.25% + 1rem);
    }
    .post > article > h2:has(+ .publications),
    .post > article > .publications {
      margin-right: 0;
    }
  }
  .profile .more-info {
    font-size: 0.85rem;
  }
  .post > .post-header {
    padding-bottom: 0.75rem;
    margin-bottom: 1.25rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .post > article > p:first-of-type {
    margin-top: 0;
  }
  .publications .abbr {
    display: none;
  }
  .publications .col-sm-8 {
    flex: 0 0 100%;
    max-width: 100%;
  }
</style>

Currently, my research follows two directions:

<div class="research" markdown="1">

<details markdown="1">
<summary><b>Lipid vesicles</b> — curvature-induced leaflet asymmetry and vesicle equilibration</summary>

I study how membrane curvature induces asymmetry in cholesterol flip-flop dynamics and phase behavior in DPPC/cholesterol vesicles. Building on the asymmetry found in binary vesicles, I am extending my research to more complex ternary vesicles known to form raft-like domains. To investigate phase behavior in these systems under well-defined equilibrium conditions, I am currently developing a vesicle equilibration methodology based on hybrid Monte Carlo–molecular dynamics.

</details>

<details markdown="1">
<summary><b>Metallic glasses</b> — fatigue behavior with machine-learning interatomic potentials</summary>

The general mechanism underlying the low fatigue limit of metallic glasses remains unclear. To investigate this problem across a broad range of compositions, I developed a machine-learning interatomic potential (MLIP) trained on DFT data. I am now studying the relationship between local atomic structure and atomic rearrangements to uncover the microscopic mechanisms of fatigue in metallic glasses.

</details>

</div>
