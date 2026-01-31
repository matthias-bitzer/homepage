---
layout: default
title: Home
---

<div class="hero">
  <h1 class="hero-title">Matthias Bitzer</h1>
  <p class="hero-subtitle">Your story, beautifully told. Exploring the intersection of AI, machine learning, and creative expression.</p>
</div>

<section class="section">
  <div class="section-header">
    <h2>AI Art Gallery</h2>
    <a href="{{ '/gallery/' | relative_url }}" class="section-link">View all &rarr;</a>
  </div>
  <p>Art created with the help of AI. The current series explores meditation and Buddhism in a futuristic style.</p>
  <div class="gallery-grid" style="margin-top: 1.5rem;">
    <figure class="gallery-item">
      <img src="{{ '/assets/images/gallery/buddha-enlightened.jpg' | relative_url }}" alt="The enlightened Buddha" loading="lazy">
      <figcaption>The enlightened Buddha</figcaption>
    </figure>
    <figure class="gallery-item">
      <img src="{{ '/assets/images/gallery/sci-fi-monk.jpg' | relative_url }}" alt="Sci-Fi Monk" loading="lazy">
      <figcaption>Sci-Fi Monk</figcaption>
    </figure>
    <figure class="gallery-item">
      <img src="{{ '/assets/images/gallery/buddha-tree.jpg' | relative_url }}" alt="Buddha under a tree" loading="lazy">
      <figcaption>Buddha under a tree</figcaption>
    </figure>
  </div>
</section>

<section class="section">
  <div class="section-header">
    <h2>Recent Blog Posts</h2>
    <a href="{{ '/blog/' | relative_url }}" class="section-link">View all &rarr;</a>
  </div>
  <div class="post-list">
    {% for post in site.posts limit:3 %}
    <article class="post-card">
      <h3 class="post-card-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <time class="post-card-date" datetime="{{ post.date | date_to_xmlschema }}">
        {{ post.date | date: "%B %Y" }}
      </time>
      {% if post.excerpt %}
        <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 150 }}</p>
      {% endif %}
    </article>
    {% endfor %}
  </div>
</section>

<section class="section">
  <div class="section-header">
    <h2>About</h2>
    <a href="{{ '/about/' | relative_url }}" class="section-link">Learn more &rarr;</a>
  </div>
  <p>I write about machine learning, programming in Python, and data science/engineering. My articles are also published on Medium.</p>
</section>
