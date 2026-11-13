---
layout: page
permalink: /lab-life/
title: lab life
description: Moments from the Soft Matter Computational Chemistry Laboratory at Sogang University.
nav: true
nav_order: 5
---

<!-- To add a post: put photos in assets/img/lab_life/ and add _lab_life/YYYY-MM-DD-short-name.md with
     front matter `title`, `date`, and `images` (a list of photo paths), followed by a few lines of text. -->

<style>
  .lab-life {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(18rem, 1fr));
    gap: 1.5rem;
  }
  .lab-life .post-card {
    border: 1px solid var(--global-divider-color);
    border-radius: 6px;
    overflow: hidden;
  }
  .lab-life .post-card img {
    display: block;
    width: 100%;
    height: auto;
  }
  .lab-life .post-body {
    padding: 0.8rem 1rem 1rem;
  }
  .lab-life .post-date {
    font-size: 0.85rem;
    color: var(--global-text-color-light);
  }
  .lab-life .post-body h3 {
    font-size: 1.1rem;
    margin: 0.2rem 0 0.5rem;
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
      {% for image in post.images %}
        <img src="{{ image | relative_url }}" alt="{{ post.title }}" loading="lazy">
      {% endfor %}
      <div class="post-body">
        <div class="post-date">{{ post.date | date: "%b %-d, %Y" }}</div>
        <h3>{{ post.title }}</h3>
        {{ post.content | markdownify }}
      </div>
    </article>
  {% endfor %}
</div>
{% endif %}
