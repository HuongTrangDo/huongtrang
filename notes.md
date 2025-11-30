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
  <h3 id="ml">Machine Learning</h3>
  <div class="posts">
    {% assign ml_posts = site.posts | where: "categories", "notes_ml" | sort: "date" | reverse %}

    {% for post in ml_posts %}
    <article>

      <a href="{{ post.url | relative_url }}" class="image">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
        {% else %}
          <img src="/images/default-thumbnail.jpg" alt="{{ post.title }}">
        {% endif %}
      </a>

      <h3>{{ post.title }}</h3>
      <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>

      <p>
        {% if post.excerpt %}
          {{ post.excerpt | strip_html | truncate: 140 }}
        {% else %}
          {{ post.content | strip_html | truncate: 140 }}
        {% endif %}
      </p>

      <ul class="actions">
        <li><a href="{{ post.url | relative_url }}" class="button">Read more</a></li>
      </ul>

    </article>
    {% endfor %}
  </div>

  <hr>

  <!-- STATISTICS SECTION -->
  <h3 id="stats">Statistics</h3>
  <div class="posts">
    {% assign stats_posts = site.posts | where: "categories", "notes_stats" | sort: "date" | reverse %}

    {% for post in stats_posts %}
    <article>

      <a href="{{ post.url | relative_url }}" class="image">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
        {% else %}
          <img src="/images/default-thumbnail.jpg" alt="{{ post.title }}">
        {% endif %}
      </a>

      <h3>{{ post.title }}</h3>
      <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>

      <p>
        {% if post.excerpt %}
          {{ post.excerpt | strip_html | truncate: 140 }}
        {% else %}
          {{ post.content | strip_html | truncate: 140 }}
        {% endif %}
      </p>

      <ul class="actions">
        <li><a href="{{ post.url | relative_url }}" class="button">Read more</a></li>
      </ul>

    </article>
    {% endfor %}
  </div>

</section>
