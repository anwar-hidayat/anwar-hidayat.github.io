---
layout: default
title: Beranda - Anwar Hidayat
---

<section class="astra-hero">
  <div class="hero-content">
    <h1>Selamat Datang di Blog Saya</h1>
    <p>Official Website from Anwar Hidayat.</p>
  </div>
</section>

<div class="astra-container">
  <main class="main-content">
    <h2 class="section-title">Artikel Terbaru</h2>
    
    <div class="post-list">
      {% for post in site.posts limit:10 %}
      <article class="post-item">
        {% if post.image %}
        <div class="post-thumbnail">
          <a href="{{ post.url | relative_url }}">
            <img src="{{ post.image }}" alt="{{ post.title }}">
          </a>
        </div>
        {% endif %}
        
        <div class="post-details">
          <header class="post-header">
            <h3 class="post-title">
              <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </h3>
            <div class="post-meta">
              <span>{{ post.date | date: "%d %B %Y" }}</span> • 
              <span>{{ post.categories | join: ", " }}</span>
            </div>
          </header>
          
          <div class="post-excerpt">
            {{ post.excerpt | strip_html | truncatewords: 30 }}
          </div>
          
          <a href="{{ post.url | relative_url }}" class="read-more">Baca Selengkapnya »</a>
        </div>
      </article>
      {% endfor %}
    </div>
  </main>
</div>

<style>
  /* ASTRA HOMEPAGE CSS INJECT */
  :root { --astra-blue: #0274be; --astra-text: #3a3a3a; --astra-light: #666; }

  .astra-hero { background: #f9f9f9; padding: 60px 20px; text-align: center; border-bottom: 1px solid #eee; margin-bottom: 40px; }
  .astra-hero h1 { font-size: 2.5rem; color: #222; margin-bottom: 10px; font-weight: 700; }
  .astra-hero p { color: var(--astra-light); font-size: 1.2rem; }

  .astra-container { max-width: 1000px; margin: 0 auto; padding: 0 20px; display: flex; gap: 40px; }
  .main-content { flex: 3; }
  
  .section-title { font-size: 1.5rem; border-bottom: 2px solid var(--astra-blue); display: inline-block; margin-bottom: 30px; padding-bottom: 5px; }

  .post-item { display: flex; gap: 25px; margin-bottom: 40px; padding-bottom: 40px; border-bottom: 1px solid #f0f0f0; align-items: flex-start; }
  .post-thumbnail { flex: 1; }
  .post-thumbnail img { width: 100%; border-radius: 4px; box-shadow: 0 4px 10px rgba(0,0,0,0.05); }
  .post-details { flex: 2; }

  .post-title { font-size: 1.8rem; margin: 0 0 10px 0; }
  .post-title a { text-decoration: none; color: #222; transition: 0.3s; }
  .post-title a:hover { color: var(--astra-blue); }

  .post-meta { font-size: 0.85rem; color: var(--astra-light); margin-bottom: 15px; text-transform: uppercase; letter-spacing: 0.5px; }
  .post-excerpt { line-height: 1.7; color: var(--astra-text); margin-bottom: 15px; }

  .read-more { font-weight: 600; color: var(--astra-blue); text-decoration: none; font-size: 0.9rem; }
  .read-more:hover { text-decoration: underline; }

  @media (max-width: 768px) {
    .post-item { flex-direction: column; }
    .astra-hero h1 { font-size: 1.8rem; }
  }
</style>
