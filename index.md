---
layout: default
title: Home
---

<div class="hero">
  <h1 class="hero-title">Matthias Bitzer</h1>
  <p class="hero-subtitle">Your story, beautifully told.</p>
</div>

<section class="section">
  <div class="section-header">
    <h2>AI Art Gallery</h2>
    <a href="{{ '/gallery/' | relative_url }}" class="section-link">View all &rarr;</a>
  </div>
  <p><strong>Januar 2023 – New AI-Art Series: Meditation/Buddha</strong></p>
  <p>This is art created with the help of <a href="https://midjourney.com" target="_blank" rel="noopener">midjourney.com</a>. The subject of this series is meditation and buddhism flavored in a futuristic style.</p>
  <div class="gallery-grid" style="margin-top: 1.5rem;">
    <figure class="gallery-item">
      <img src="{{ '/assets/images/gallery/MatthiasBitzer_buddha_sitting_in_a_forest_getting_enlighted_wit_3d6f867c-8f95-4130-95e0-b9df4d590811 (1).png' | relative_url }}" alt="The enlightened Buddha" loading="lazy">
      <figcaption>The enlightened Buddha</figcaption>
    </figure>
    <figure class="gallery-item">
      <img src="{{ '/assets/images/gallery/MatthiasBitzer_32k_hypermaximal_elegant_hyper_4k_very_colorful__6eeab6ae-df90-4339-90b2-19bef1731b3e.png' | relative_url }}" alt="Sci-Fi Monk" loading="lazy">
      <figcaption>Sci-Fi Monk</figcaption>
    </figure>
    <figure class="gallery-item">
      <img src="{{ '/assets/images/gallery/MatthiasBitzer_buddha_sitting_under_a_tree_in_a_mystical_old_sc_2bb75155-e77f-4e88-ae88-b5b8c2e4cbe1.png' | relative_url }}" alt="Buddha under a tree" loading="lazy">
      <figcaption>Buddha under a tree</figcaption>
    </figure>
  </div>
</section>

<section class="section">
  <div class="section-header">
    <h2>Matthias' AI Blog</h2>
    <a href="{{ '/blog/' | relative_url }}" class="section-link">Blog &rarr;</a>
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
    <a href="{{ '/about/' | relative_url }}" class="section-link">About &rarr;</a>
  </div>
  <p>These are blog articles, also published at <a href="https://medium.com" target="_blank" rel="noopener">medium.com</a>. The subject spans mostly machine learning, programming in python and data science/engineering.</p>
</section>
