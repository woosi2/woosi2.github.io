---
layout: page
title: News
permalink: /news/
---

<style>
  .news-years {
    display: flex;
    gap: 0.5rem;
    margin-bottom: 1.5rem;
  }
  .news-years a {
    padding: 0.25rem 0.9rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 999px;
    color: var(--global-text-color);
    text-decoration: none;
  }
  .news-years a.active {
    border-color: var(--global-theme-color);
    background: var(--global-theme-color);
    color: #fff;
  }
  .news-year th {
    width: 1%;
    white-space: nowrap;
    padding-right: 1.5rem;
  }
</style>

{% assign years = site.news | group_by_exp: "item", "item.date | date: '%Y'" | sort: "name" %}

<nav class="news-years">
  {% for year in years %}
    <a href="#{{ year.name }}">{{ year.name }}</a>
  {% endfor %}
</nav>
{% for year in years %}
  {% assign items = year.items | sort: "date" | reverse %}
  <section class="news-year" id="{{ year.name }}">
    <table class="table table-sm table-borderless">
      {% for item in items %}
        <tr>
          <th scope="row">{{ item.date | date: "%b %-d, %Y" }}</th>
          <td>
            {% if item.inline %}
              {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
            {% else %}
              <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
            {% endif %}
          </td>
        </tr>
      {% endfor %}
    </table>
  </section>
{% endfor %}

<script>
  // Year tabs: show one year at a time (the latest by default, or the one in the URL hash).
  const newsTabs = document.querySelectorAll(".news-years a");
  const newsYears = document.querySelectorAll(".news-year");
  const showNewsYear = (y) => {
    if (![...newsYears].some((s) => s.id === y)) y = newsYears[newsYears.length - 1].id;
    newsYears.forEach((s) => (s.hidden = s.id !== y));
    newsTabs.forEach((t) => t.classList.toggle("active", t.hash === "#" + y));
  };
  newsTabs.forEach((t) =>
    t.addEventListener("click", (e) => {
      e.preventDefault();
      showNewsYear(t.hash.slice(1));
      history.replaceState(null, "", t.hash);
    }),
  );
  if (newsYears.length) showNewsYear(location.hash.slice(1));
</script>
