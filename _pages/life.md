---
layout: page
permalink: /lab-life/
title: lab life
description: Moments from the Soft Matter Computational Chemistry Laboratory at Sogang University.
nav: true
nav_order: 5
---

<!-- To add a post: put photos in assets/img/lab_life/ and add _lab_life/YYYY-MM-DD-short-name.md with
     front matter `title`, `date` (optional `date_end`), and `images` (a list of `src` + optional `caption`),
     followed by a couple of lines of text. Posts are grouped into year tabs automatically. -->

<style>
  .lab-life .years {
    display: flex;
    gap: 0.5rem;
    margin-bottom: 0.5rem;
  }
  .lab-life .years a {
    padding: 0.25rem 0.9rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 999px;
    color: var(--global-text-color);
    text-decoration: none;
  }
  .lab-life .years a.active {
    border-color: var(--global-theme-color);
    background: var(--global-theme-color);
    color: #fff;
  }
  .lab-life .post-row {
    display: grid;
    grid-template-columns: minmax(0, 3fr) minmax(0, 2fr);
    gap: 2.5rem;
    align-items: center;
    padding: 1.75rem 0;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .lab-life .post-row:nth-child(even) {
    grid-template-columns: minmax(0, 2fr) minmax(0, 3fr);
  }
  .lab-life .post-row:nth-child(even) .carousel {
    order: -1;
  }
  .lab-life .post-date {
    font-size: 0.85rem;
    color: var(--global-text-color-light);
  }
  .lab-life .post-text h3 {
    font-size: 1.2rem;
    font-style: italic;
    margin: 0.2rem 0 0.75rem;
    padding-bottom: 0.6rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .lab-life .post-text p:last-child {
    margin-bottom: 0;
  }
  .lab-life .carousel {
    position: relative;
  }
  .lab-life .track {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    scrollbar-width: none;
  }
  .lab-life .track::-webkit-scrollbar {
    display: none;
  }
  .lab-life .slide {
    flex: 0 0 100%;
    margin: 0;
    scroll-snap-align: center;
  }
  .lab-life .slide img {
    display: block;
    width: 100%;
    aspect-ratio: 4 / 3;
    object-fit: contain;
  }
  .lab-life .slide figcaption {
    padding: 0.5rem 0.25rem 0;
    text-align: center;
    font-size: 0.85rem;
    color: var(--global-text-color-light);
  }
  .lab-life .nav-btn {
    position: absolute;
    top: 0;
    margin-top: calc(37.5% - 1rem);
    width: 2rem;
    height: 2rem;
    border: none;
    border-radius: 50%;
    background: rgba(0, 0, 0, 0.45);
    color: #fff;
    font-size: 1.2rem;
    line-height: 1;
    cursor: pointer;
    opacity: 0.8;
  }
  .lab-life .nav-btn:hover {
    opacity: 1;
  }
  .lab-life .nav-btn.prev {
    left: 0.5rem;
  }
  .lab-life .nav-btn.next {
    right: 0.5rem;
  }
  .lab-life .nav-btn:disabled {
    visibility: hidden;
  }
  .lab-life .dots {
    display: flex;
    justify-content: center;
    gap: 0.4rem;
    padding-top: 0.6rem;
  }
  .lab-life .dots button {
    width: 0.5rem;
    height: 0.5rem;
    padding: 0;
    border: none;
    border-radius: 50%;
    background: var(--global-divider-color);
    cursor: pointer;
  }
  .lab-life .dots button.active {
    background: var(--global-theme-color);
  }
  @media (max-width: 767px) {
    .lab-life .post-row {
      grid-template-columns: minmax(0, 1fr);
      gap: 1rem;
    }
    .lab-life .post-row:nth-child(even) {
      grid-template-columns: minmax(0, 1fr);
    }
    .lab-life .post-row:nth-child(even) .carousel {
      order: 0;
    }
  }
</style>

{% assign years = site.lab_life | group_by_exp: "post", "post.date | date: '%Y'" | sort: "name" %}
{% if years.size == 0 %}

<p>Photos and notes from lab life will appear here soon.</p>
{% else %}
<div class="lab-life">
  <nav class="years">
    {% for year in years %}
      <a href="#{{ year.name }}">{{ year.name }}</a>
    {% endfor %}
  </nav>
  {% for year in years %}
    {% assign posts = year.items | sort: "date" | reverse %}
    <section class="year" id="{{ year.name }}">
      {% for post in posts %}
        <article class="post-row">
          <div class="post-text">
            {% assign m0 = post.date | date: "%b" %}
            <div class="post-date">
              {% if post.date_end %}
                {% assign m1 = post.date_end | date: "%b" %}
                {% if m1 == m0 %}
                  {{ m0 }} {{ post.date | date: "%-d" }}–{{ post.date_end | date: "%-d" }}, {{ post.date | date: "%Y" }}
                {% else %}
                  {{ m0 }} {{ post.date | date: "%-d" }} – {{ post.date_end | date: "%b %-d" }}, {{ post.date | date: "%Y" }}
                {% endif %}
              {% else %}
                {{ post.date | date: "%b %-d, %Y" }}
              {% endif %}
            </div>
            <h3>{{ post.title }}</h3>
            {{ post.content | markdownify }}
          </div>
          <div class="carousel">
            <div class="track">
              {% for image in post.images %}
                <figure class="slide">
                  <img src="{{ image.src | relative_url }}" alt="{{ image.caption | default: post.title | escape }}" loading="lazy">
                  {% if image.caption %}<figcaption>{{ image.caption | escape }}</figcaption>{% endif %}
                </figure>
              {% endfor %}
            </div>
            {% if post.images.size > 1 %}
              <button class="nav-btn prev" aria-label="Previous photo">&#8249;</button>
              <button class="nav-btn next" aria-label="Next photo">&#8250;</button>
              <div class="dots">
                {% for image in post.images %}
                  <button aria-label="Photo {{ forloop.index }}"></button>
                {% endfor %}
              </div>
            {% endif %}
          </div>
        </article>
      {% endfor %}
    </section>
  {% endfor %}
</div>
{% endif %}

<script>
  // Year tabs: show one year at a time (the latest by default, or the one in the URL hash).
  const tabs = document.querySelectorAll(".lab-life .years a");
  const sections = document.querySelectorAll(".lab-life .year");
  const showYear = (y) => {
    if (![...sections].some((s) => s.id === y)) y = sections[sections.length - 1].id;
    sections.forEach((s) => (s.hidden = s.id !== y));
    tabs.forEach((t) => t.classList.toggle("active", t.hash === "#" + y));
    document.querySelectorAll(".lab-life .carousel").forEach((c) => c.update && c.update());
  };
  tabs.forEach((t) =>
    t.addEventListener("click", (e) => {
      e.preventDefault();
      showYear(t.hash.slice(1));
      history.replaceState(null, "", t.hash);
    }),
  );

  // Slideshows: arrows, dots, and swipe.
  document.querySelectorAll(".lab-life .carousel").forEach((c) => {
    const track = c.querySelector(".track");
    const dots = c.querySelectorAll(".dots button");
    if (!dots.length) return;
    const prev = c.querySelector(".prev");
    const next = c.querySelector(".next");
    const go = (i) => track.scrollTo({ left: i * track.clientWidth, behavior: "smooth" });
    const index = () => Math.round(track.scrollLeft / (track.clientWidth || 1));
    c.update = () => {
      const i = index();
      dots.forEach((d, k) => d.classList.toggle("active", k === i));
      prev.disabled = i === 0;
      next.disabled = i === dots.length - 1;
    };
    dots.forEach((d, k) => d.addEventListener("click", () => go(k)));
    prev.addEventListener("click", () => go(index() - 1));
    next.addEventListener("click", () => go(index() + 1));
    track.addEventListener("scroll", c.update, { passive: true });
    c.update();
  });

  if (sections.length) showYear(location.hash.slice(1));
</script>
