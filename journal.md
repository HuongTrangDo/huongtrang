---
layout: default
title: Life Journal
permalink: /journal/
pagination:
  enabled: true
  category: journal
  per_page: 6
---

# Life Journal  
_Tiny memories — gentle moments._

---

## 🔍 Filter by Year

{% assign years = site.categories.journal | map: "date" | map: "year" | uniq | sort | reverse %}

<form method="get" id="filter">
  <label>Select year:</label>
  <select name="year" onchange="this.form.submit()">
    <option value="">All</option>
    {% for y in years %}
      <option value="{{ y }}" {% if y == page.year %}selected{% endif %}>{{ y }}</option>
    {% endfor %}
  </select>
</form>

---

## 📘 Journal Entries

<div class="posts">

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
    <p class="date">{{ post.date | date: "%B %d, %Y" }}</p>

    <a href="{{ post.url }}" class="button small">Read more</a>
  </article>
{% endfor %}

</div>

---

## 📄 Pagination

<ul class="pagination">
  {% if paginator.previous_page %}
    <li><a href="{{ paginator.previous_page_path }}">← Prev</a></li>
  {% endif %}

  {% for p in (1..paginator.total_pages) %}
    <li>
      <a href="/journal/page{{ p }}" class="{% if p == paginator.page %}active{% endif %}">
        {{ p }}
      </a>
    </li>
  {% endfor %}

  {% if paginator.next_page %}
    <li><a href="{{ paginator.next_page_path }}">Next →</a></li>
  {% endif %}
</ul>
