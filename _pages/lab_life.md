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
     optionally followed by a line of text. Several images become a swipeable slideshow. -->

<style>
  .lab-life {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(20rem, 1fr));
    gap: 1.5rem;
  }
  .lab-life .post-card {
    border: 1px solid var(--global-divider-color);
    border-radius: 6px;
    overflow: hidden;
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
    background: var(--global-divider-color);
  }
  .lab-life .slide figcaption {
    padding: 0.5rem 1rem 0;
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
    padding: 0.6rem 0 0;
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
  .lab-life .post-body {
    padding: 0.6rem 1rem 1rem;
  }
  .lab-life .post-date {
    font-size: 0.85rem;
    color: var(--global-text-color-light);
  }
  .lab-life .post-body h3 {
    font-size: 1.1rem;
    margin: 0.2rem 0 0;
  }
  .lab-life .post-body p:first-of-type {
    margin-top: 0.5rem;
  }
  .lab-life .post-body p:last-child {
    margin-bottom: 0;
  }
</style>

{% assign posts = site.lab_life | sort: "date" | reverse %}
{% if posts.size == 0 %}

<p>Photos and notes from lab life will appear here soon.</p>
{% else %}
<div class="lab-life">
  {% for post in posts %}
    <article class="post-card">
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
      <div class="post-body">
        {% assign y0 = post.date | date: "%Y" %}{% assign m0 = post.date | date: "%b" %}
        <div class="post-date">
          {% if post.date_end %}
            {% assign m1 = post.date_end | date: "%b" %}
            {% if m1 == m0 %}{{ m0 }} {{ post.date | date: "%-d" }}–{{ post.date_end | date: "%-d" }}, {{ y0 }}{% else %}{{ m0 }} {{ post.date | date: "%-d" }} – {{ post.date_end | date: "%b %-d" }}, {{ y0 }}{% endif %}
          {% else %}
            {{ post.date | date: "%b %-d, %Y" }}
          {% endif %}
        </div>
        <h3>{{ post.title }}</h3>
        {{ post.content | markdownify }}
      </div>
    </article>
  {% endfor %}
</div>
{% endif %}

<script>
  document.querySelectorAll(".lab-life .carousel").forEach((c) => {
    const track = c.querySelector(".track");
    const dots = c.querySelectorAll(".dots button");
    if (!dots.length) return;
    const prev = c.querySelector(".prev");
    const next = c.querySelector(".next");
    const go = (i) => track.scrollTo({ left: i * track.clientWidth, behavior: "smooth" });
    const index = () => Math.round(track.scrollLeft / track.clientWidth);
    const update = () => {
      const i = index();
      dots.forEach((d, k) => d.classList.toggle("active", k === i));
      prev.disabled = i === 0;
      next.disabled = i === dots.length - 1;
    };
    dots.forEach((d, k) => d.addEventListener("click", () => go(k)));
    prev.addEventListener("click", () => go(index() - 1));
    next.addEventListener("click", () => go(index() + 1));
    track.addEventListener("scroll", update, { passive: true });
    update();
  });
</script>
