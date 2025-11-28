---
layout: default
title: Life Journal
permalink: /journal/
pagination:
  enabled: true
  category: journal
  per_page: 10
---

<section>
  <header class="major">
    <h2>Life Journal</h2>
  </header>

  <div class="posts">

    {% for post in paginator.posts %}
    <article>
      <a href="{{ post.url }}" class="image">
        <img src="{{ post.image }}" alt="">
      </a>

      <h3>{{ post.title }}</h3>

      <p>
        {{ post.excerpt | strip_html | truncate: 130 }}
      </p>

      <ul class="actions">
        <li><a href="{{ post.url }}" class="button">More</a></li>
      </ul>
    </article>
    {% endfor %}

  </div>
</section>

<!-- Pagination (Previous / Next) -->
<ul class="pagination">
  {% if paginator.previous_page %}
    <li><a href="{{ paginator.previous_page_path }}">← Previous</a></li>
  {% endif %}

  <li>Page {{ paginator.page }} of {{ paginator.total_pages }}</li>

  {% if paginator.next_page %}
    <li><a href="{{ paginator.next_page_path }}">Next →</a></li>
  {% endif %}
</ul>
