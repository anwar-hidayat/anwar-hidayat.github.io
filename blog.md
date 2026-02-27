---
layout: default
title: "Blog - Artikel Terbaru"
permalink: /blog/
---

<div class="astra-blog-wrapper">
  <header class="blog-header">
    <h1>Arsip Artikel</h1>
    <p>Berbagi wawasan, tutorial, dan berita terbaru.</p>
  </header>

  <div class="astra-post-grid">
    {% for post in site.posts %}
    <article class="astra-card">
      {% if post.image %}
      <div class="card-image">
        <a href="{{ post.url | relative_url }}">
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
        </a>
      </div>
      {% endif %}
      
      <div class="card-content">
        <span class="card-meta">{{ post.date | date: "%B %d, %Y" }} • {{ post.categories | first | capitalize }}</span>
        <h2 class="card-title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h2>
        <p class="card-excerpt">
          {{ post.excerpt | strip_html | truncatewords: 25 }}
        </p>
        <a href="{{ post.url | relative_url }}" class="read-more">Baca Selengkapnya »</a>
      </div>
    </article>
    {% endfor %}
  </div>
</div>

<style>
  :root {
    --astra-blue: #0274be;
    --astra-text: #3a3a3a;
    --astra-meta: #666;
    --bg-light: #f5f7f9;
  }

  .astra-blog-wrapper {
    max-width: 1000px;
    margin: 40px auto;
    padding: 0 20px;
  }

  .blog-header {
    text-align: center;
    margin-bottom: 50px;
  }

  .blog-header h1 {
    font-size: 2.5rem;
    color: #222;
    margin-bottom: 10px;
  }

  /* Grid Layout */
  .astra-post-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 30px;
  }

  /* Card Style */
  .astra-card {
    background: #fff;
    border-radius: 4px;
    overflow: hidden;
    transition: transform 0.3s, box-shadow 0.3s;
    border: 1px solid #eaeaea;
    display: flex;
    flex-direction: column;
  }

  .astra-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 25px rgba(0,0,0,0.08);
  }

  .card-image img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    display: block;
  }

  .card-content {
    padding: 25px;
    flex-grow: 1;
  }

  .card-meta {
    display: block;
    font-size: 12px;
    text-transform: uppercase;
    color: var(--astra-meta);
    letter-spacing: 1px;
    margin-bottom: 10px;
  }

  .card-title {
    margin: 0 0 15px 0;
    font-size: 1.4rem;
    line-height: 1.3;
  }

  .card-title a {
    text-decoration: none;
    color: #222;
    transition: 0.2s;
  }

  .card-title a:hover {
    color: var(--astra-blue);
  }

  .card-excerpt {
    color: #555;
    font-size: 15px;
    line-height: 1.6;
    margin-bottom: 20px;
  }

  .read-more {
    color: var(--astra-blue);
    text-decoration: none;
    font-weight: 600;
    font-size: 14px;
    text-transform: uppercase;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .astra-post-grid { grid-template-columns: 1fr; }
  }
</style>
