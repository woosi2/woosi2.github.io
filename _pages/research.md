---
layout: page
title: Research
permalink: /research/
description: Research projects on lipid membranes and metallic glasses, connecting microscopic structure and dynamics to macroscopic behavior through molecular simulation.
nav: true
nav_order: 2
_styles: |
  .post:has(.research-projects) > .post-header .post-title { font-weight: 700; }
  .post:has(.research-projects) > .post-header .post-description { max-width: 78ch; line-height: 1.75; margin-top: 0.75rem; }
  .research-projects { --research-muted: color-mix(in srgb, var(--global-text-color) 68%, var(--global-bg-color)); --research-border: color-mix(in srgb, var(--global-text-color) 13%, var(--global-bg-color)); --research-surface: color-mix(in srgb, var(--global-text-color) 1.5%, var(--global-bg-color)); margin-top: 2.75rem; }
  .research-projects .research-project-group + .research-project-group { margin-top: 3.5rem; }
  .research-projects .research-project-group > h2 { font-size: 1.5rem; font-weight: 600; line-height: 1.35; margin: 0 0 1.25rem; }
  .research-projects .research-project-card { scroll-margin-top: 6rem; display: grid; grid-template-columns: 32% minmax(0, 1fr); overflow: hidden; border: 1px solid var(--research-border); border-radius: 4px; background: var(--global-bg-color); margin-bottom: 1.5rem; }
  .research-projects .research-project-card--text { grid-template-columns: minmax(0, 1fr); }
  .research-projects .research-project-visual { display: flex; flex-direction: column; align-items: center; justify-content: center; min-width: 0; margin: 1.25rem 0 1.25rem 1.25rem; }
  .research-projects .research-project-visual img { display: block; width: 100%; height: auto; object-fit: contain; }
  .research-projects .research-project-content { display: flex; flex-direction: column; min-width: 0; padding: 1.75rem 1.75rem 1.5rem; }
  .research-projects .research-project-content h3 { font-size: 1.45rem; font-weight: 700; line-height: 1.3; letter-spacing: -0.015em; margin: 0 0 0.75rem; }
  .research-projects .research-project-meta { font-size: 0.8rem; line-height: 1.65; margin: 0 0 1rem; color: var(--research-muted); }
  .research-projects .research-project-summary { font-size: 0.98rem; line-height: 1.8; margin: 0 0 1rem; }
  .research-projects .research-project-methods { font-size: 0.8rem; line-height: 1.7; margin: 0 0 1.25rem; color: var(--research-muted); }
  .research-projects .research-project-methods span { font-weight: 500; color: var(--global-text-color); }
  .research-projects .research-project-actions { display: flex; align-items: baseline; flex-wrap: wrap; gap: 0.65rem 1.25rem; margin-top: auto; padding-top: 0.5rem; }
  .research-projects .research-project-links { display: flex; flex-wrap: wrap; gap: 0.5rem 1rem; list-style: none; margin: 0; padding: 0; font-size: 0.85rem; }
  .research-projects .research-project-links a { color: var(--global-text-color); text-decoration: underline; text-decoration-color: var(--research-border); text-underline-offset: 0.25em; }
  .research-projects .research-project-links a:hover { color: var(--global-theme-color); text-decoration-color: currentColor; }
  .research-projects a:focus-visible, .research-projects button:focus-visible { outline: 2px solid var(--global-theme-color); outline-offset: 4px; }
  .research-projects .research-project-group--additional > h2 { font-size: 1.35rem; }
  .research-projects .research-project-group--additional .research-project-content { padding: 1.4rem 1.5rem; }
  .research-projects .research-project-group--additional .research-project-content h3 { font-size: 1.2rem; line-height: 1.4; }
  .research-projects .research-project-group--additional .research-project-summary { font-size: 0.95rem; line-height: 1.75; margin-bottom: 0; }
  .research-projects .research-details-toggle { padding: 0; border: 0; background: transparent; color: var(--research-muted); font-family: inherit; font-size: 0.85rem; line-height: 1.65; cursor: pointer; text-decoration: underline; text-decoration-color: var(--research-border); text-underline-offset: 0.25em; }
  .research-projects .research-details-toggle:hover, .research-projects .research-details-toggle[aria-expanded='true'] { color: var(--global-theme-color); text-decoration-color: currentColor; }
  .research-projects .research-project-details { grid-column: 1 / -1; overflow: hidden; border-top: 1px solid var(--research-border); background: var(--research-surface); }
  .research-projects .research-project-details[hidden] { display: none; }
  .research-projects .research-details-inner { padding: 1.75rem; }
  .research-projects .research-details-inner > p { max-width: 78ch; font-size: 0.95rem; line-height: 1.8; margin: 0 0 1rem; }
  .research-projects .research-detail-figures { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 1.5rem; margin: 1.5rem 0; align-items: start; }
  .research-projects .research-detail-figures figure { min-width: 0; margin: 0; }
  .research-projects .research-detail-figures img { width: 100%; height: auto; object-fit: contain; }
  .research-projects .research-detail-figures figcaption { font-size: 0.8rem; line-height: 1.6; margin-top: 0.65rem; color: var(--research-muted); font-style: italic; text-align: center; }
  .research-projects .research-related-papers { margin-top: 1.5rem; }
  .research-projects .research-related-papers h4 { font-size: 1.05rem; font-weight: 600; line-height: 1.4; margin: 0 0 0.75rem; scroll-margin-top: 6rem; }
  .research-projects .research-related-papers ul { padding-left: 1.2rem; margin: 0; font-size: 0.9rem; line-height: 1.75; }
  .research-projects .research-related-papers li + li { margin-top: 0.75rem; }
  @media (max-width: 767px) {
    .research-projects { margin-top: 2rem; }
    .research-projects .research-project-card { grid-template-columns: minmax(0, 1fr); }
    .research-projects .research-project-visual { margin: 1.25rem 1.25rem 0; }
    .research-projects .research-project-content, .research-projects .research-project-group--additional .research-project-content { padding: 1.25rem; }
    .research-projects .research-project-content h3 { font-size: 1.3rem; line-height: 1.35; }
    .research-projects .research-project-group--additional .research-project-content h3 { font-size: 1.15rem; }
    .research-projects .research-details-inner { padding: 1.25rem; }
    .research-projects .research-detail-figures { grid-template-columns: minmax(0, 1fr); }
  }
---

<!-- Content lives in _data/research.yml. -->
<div class="research-projects">
  {% assign groups = 'featured,additional' | split: ',' %}
  {% for group in groups %}
  {% assign projects = site.data.research.projects | where: 'group', group %}
  {% if projects.size > 0 %}
  <section class="research-project-group research-project-group--{{ group }}" aria-labelledby="{{ group }}-research-heading">
    <h2 id="{{ group }}-research-heading">{% if group == 'featured' %}Featured Research{% else %}Additional Research Projects{% endif %}</h2>
    {% for project in projects %}
    <article class="research-project-card{% unless project.image %} research-project-card--text{% endunless %}" id="{{ project.id }}" aria-labelledby="{{ project.id }}-title">
      {% if project.image %}
      <figure class="research-project-visual">
        <img src="{{ project.image | relative_url }}" alt="{{ project.image_alt | escape }}" loading="lazy" data-zoomable>
      </figure>
      {% endif %}
      <div class="research-project-content">
        <h3 id="{{ project.id }}-title">{{ project.title }}</h3>
        <p class="research-project-meta">{{ project.period }}{% if project.funding %} · {{ project.funding }}{% endif %}</p>
        <p class="research-project-summary">{{ project.description }}</p>
        {% if project.methods %}
        <p class="research-project-methods"><span>Methods / Focus:</span> {{ project.methods }}</p>
        {% endif %}
        {% if group == 'featured' %}
        <div class="research-project-actions">
          {% if project.papers.size > 0 %}
          <ul class="research-project-links" aria-label="Related publications">
            <li><a href="#{{ project.id }}-related-papers" data-output-details="{{ project.id }}-details" data-output-focus="{{ project.id }}-related-papers">Papers</a></li>
          </ul>
          {% endif %}
          <button class="research-details-toggle" type="button" aria-expanded="false" aria-controls="{{ project.id }}-details">More details ↓</button>
        </div>
        {% endif %}
      </div>
      {% if group == 'featured' %}
      <div class="research-project-details" id="{{ project.id }}-details" hidden>
        <div class="research-details-inner">
          {% for paragraph in project.details %}
          <p>{{ paragraph }}</p>
          {% endfor %}
          {% if project.figures.size > 0 %}
          <div class="research-detail-figures">
            {% for figure in project.figures %}
            <figure><img src="{{ figure.image | relative_url }}" alt="{{ figure.alt | escape }}" loading="lazy" data-zoomable>{% if figure.caption %}<figcaption>{{ figure.caption }}</figcaption>{% endif %}</figure>
            {% endfor %}
          </div>
          {% endif %}
          {% if project.papers.size > 0 %}
          <section class="research-related-papers" aria-labelledby="{{ project.id }}-related-papers">
            <h4 id="{{ project.id }}-related-papers" tabindex="-1">Related Papers</h4>
            <ul>
              {% for paper in project.papers %}
              <li>{% if paper.url %}<a href="{{ paper.url | escape }}" target="_blank" rel="noopener noreferrer">{{ paper.citation }}</a>{% else %}{{ paper.citation }}{% endif %}</li>
              {% endfor %}
            </ul>
          </section>
          {% endif %}
        </div>
      </div>
      {% endif %}
    </article>
    {% endfor %}
  </section>
  {% endif %}
  {% endfor %}
</div>

<script>
  (() => {
    const animations = new WeakMap();
    function setExpanded(button, expanded, animate = true) {
      const panel = document.getElementById(button.getAttribute("aria-controls"));
      const previous = animations.get(panel);
      if (previous) previous.cancel();
      button.setAttribute("aria-expanded", String(expanded));
      button.textContent = expanded ? "Less ↑" : "More details ↓";
      panel.hidden = false;
      if (!animate || window.matchMedia("(prefers-reduced-motion: reduce)").matches) {
        panel.hidden = !expanded;
        return;
      }
      const height = panel.scrollHeight;
      const animation = panel.animate([{ height: expanded ? "0px" : `${height}px` }, { height: expanded ? `${height}px` : "0px" }], {
        duration: 180,
        easing: "ease-out",
      });
      animations.set(panel, animation);
      animation.onfinish = () => {
        panel.hidden = !expanded;
        animations.delete(panel);
      };
    }
    document.querySelectorAll(".research-details-toggle").forEach((button) => {
      button.addEventListener("click", () => setExpanded(button, button.getAttribute("aria-expanded") !== "true"));
    });
    document.querySelectorAll("[data-output-details]").forEach((link) => {
      link.addEventListener("click", (event) => {
        const button = document.querySelector(`[aria-controls="${link.dataset.outputDetails}"]`);
        if (button) setExpanded(button, true, false);
        const focusTarget = document.getElementById(link.dataset.outputFocus);
        if (focusTarget) {
          event.preventDefault();
          if (window.location.hash !== link.hash) window.history.pushState(null, "", link.hash);
          focusTarget.focus({ preventScroll: true });
          focusTarget.scrollIntoView({ block: "start" });
        }
      });
    });
    function revealHash() {
      const target = document.getElementById(window.location.hash.slice(1));
      const panel = target?.closest(".research-project-details");
      if (!panel) return;
      const button = document.querySelector(`[aria-controls="${panel.id}"]`);
      if (button) {
        setExpanded(button, true, false);
        target.scrollIntoView();
      }
    }
    window.addEventListener("hashchange", revealHash);
    revealHash();
  })();
</script>
