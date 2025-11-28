---
layout: default
title: Life Journal
permalink: /journal/
pagination:
  enabled: true
  category: journal
  per_page: 6
---

<header class="major">
  <h2>Life Journal</h2>
  <p>Tiny memories — gentle moments.</p>
</header>

<!-- FILTER theo năm -->
{% assign years = site.categories.journal | map: "date" | map: "year" | uniq | sort | reverse %}

<form method="get" id="filter">
  <label>Filter by year:</label>
  <select name="year" onchange="this.form.submit()">
    <option value="">All</option>
    {% for y in years %}
      <option value="{{ y }}" {% if y == page.year %}selected{% endif %}>{{ y }}</option>
    {% endfor %}
  </select>
</form>

<!-- Danh sách bài -->
<section class="posts">

{% assign posts = paginator.posts %}
{% if page.year %}
  {% assign posts = posts | where_exp: "post", "post.date | date: '%Y' == page.year" %}
{% endif %}

{% for post in posts %}
  <article>
    <a href="{{ post.url }}" class="image">
      <img src="{{ post.image }}" alt="">
    </a>
    <h3>{{ post.title }}</h3>
    <p>{{ post.date | date: "%B %d, %Y" }}</p>

    <ul class="actions">
      <li><a href="{{ post.url }}" class="button">Read</a></li>
    </ul>
  </article>
{% endfor %}

</section>

<!-- Pagination -->
<ul class="pagination">
  {% if paginator.previous_page %}
    <li><a href="{{ paginator.previous_page_path }}" class="page">Prev</a></li>
  {% endif %}

  {% for p in (1..paginator.total_pages) %}
    <li>
      <a href="/journal/page{{ p }}" class="page {% if p == paginator.page %}active{% endif %}">
        {{ p }}
      </a>
    </li>
  {% endfor %}

  {% if paginator.next_page %}
    <li><a href="{{ paginator.next_page_path }}" class="page">Next</a></li>
  {% endif %}
</ul>
