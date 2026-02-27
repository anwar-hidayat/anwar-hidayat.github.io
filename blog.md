---
layout: default
title: "Blog"
permalink: /blog/
---

<div class="blog-container">
  <h1>Artikel Terbaru</h1>
  <hr>
  
  <ul class="post-list">
    {% for post in site.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
        <p>{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
      </li>
    {% endfor %}
  </ul>
</div>

<style>
  .post-list { list-style: none; padding: 0; }
  .post-list li { margin-bottom: 30px; border-bottom: 1px solid #eee; padding-bottom: 20px; }
  .post-meta { color: #888; font-size: 14px; }
  .post-link { color: #0274be; text-decoration: none; font-size: 22px; font-weight: bold; }
</style>
