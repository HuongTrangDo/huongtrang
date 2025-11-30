---
layout: default
title: Notes
permalink: /notes/
---

<section>
  <header class="major">
    <h2>Notes</h2>
  </header>

  <!-- MACHINE LEARNING SECTION -->
  <h3>Machine Learning</h3>
  <div class="posts">
    {% assign ml_posts = site.posts | where: "categories", "notes_ml" | sort: "date" | reverse %}

    {% for post in ml_posts %}
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

  <hr>

  <!-- STATISTICS SECTION -->
  <h3>Statistics</h3>
  <div class="posts">
    {% assign stats_posts = site.posts | where: "categories", "notes_stats" | sort: "date" | reverse %}

    {% for post in stats_posts %}
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
