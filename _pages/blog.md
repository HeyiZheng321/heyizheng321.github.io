---
layout: default
permalink: /blog/
title: blog
nav: true
nav_order: 4
description: Occasional notes on research, data, and cities.
---

<div class="minimal-page blog-index">
  <h1 class="minimal-page-title">Blog</h1>
  <p class="minimal-lead">Occasional notes on research, data, and cities.</p>

  {% assign note_count = 0 %}
  <ul class="minimal-list">
    {% for post in site.posts %}
      {% if post.category == "notes" or post.categories contains "notes" %}
        {% assign note_count = note_count | plus: 1 %}
        <li class="minimal-item">
          <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
          {% if post.description %}<p>{{ post.description }}</p>{% endif %}
          <p class="minimal-meta">{{ post.date | date: '%B %d, %Y' }}</p>
        </li>
      {% endif %}
    {% endfor %}
  </ul>

  {% if note_count == 0 %}
    <p class="minimal-empty">No posts yet. New notes will appear here.</p>
    <p class="minimal-meta">To publish a note, add a Markdown file to <code>_posts/</code> with <code>category: notes</code>.</p>
  {% endif %}
</div>
