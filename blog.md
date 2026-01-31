---
layout: default
title: Blog
permalink: /blog/
---

<header class="page-header">
  <h1>AI/ML Blog</h1>
  <p class="page-description">Articles about machine learning, Python programming, and data science/engineering. Also published on Medium.</p>
</header>

<div class="post-list">
  {% for post in site.posts %}
  <article class="post-card">
    <h2 class="post-card-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>
    <time class="post-card-date" datetime="{{ post.date | date_to_xmlschema }}">
      {{ post.date | date: "%B %Y" }}
    </time>
    {% if post.excerpt %}
      <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 200 }}</p>
    {% endif %}
  </article>
  {% endfor %}
</div>

{% if site.posts.size == 0 %}
<p style="text-align: center; color: var(--color-text-secondary);">No blog posts yet. Check back soon!</p>
{% endif %}
