---
layout: default
title: Life Journal
permalink: /journal/
---

<section>
  <header class="major">
    <h2>Life Journal</h2>
  </header>

  <div class="posts">

    {% assign journal_posts = site.categories.journal | sort: "date" | reverse %}

    {% for post in journal_posts limit: 10 %}
    <article>

      <!-- Thumbnail -->
      <a href="{{ post.url | relative_url }}" class="image">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
        {% else %}
          <img src="/images/default-thumbnail.jpg" alt="{{ post.title }}">
        {% endif %}
      </a>

      <!-- Title -->
      <h3>{{ post.title }}</h3>

      <!-- Date -->
      <p class="post-meta">
        {{ post.date | date: "%B %d, %Y" }}
      </p>

      <!-- Excerpt -->
      <p>
        {% if post.excerpt %}
          {{ post.excerpt | strip_html | truncate: 140 }}
        {% else %}
          {{ post.content | strip_html | truncate: 140 }}
        {% endif %}
      </p>

      <!-- Button -->
      <ul class="actions">
        <li><a href="{{ post.url | relative_url }}" class="button">Read more</a></li>
      </ul>

    </article>
    {% endfor %}

  </div>
</section>
