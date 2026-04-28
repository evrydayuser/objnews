---
layout: default
title: Home
---

<style>
  .hero-banner {
    background: #1a1a1a;
    color: #fff;
    padding: 40px 20px;
    text-align: center;
    border-bottom: 5px solid #d33;
    margin-bottom: 30px;
  }
  .wire-container {
    display: flex;
    flex-direction: column;
    gap: 15px;
  }
  .news-card {
    border-left: 5px solid #333;
    padding: 15px;
    background: #f9f9f9;
    transition: 0.2s;
    text-decoration: none;
    color: #000;
    display: block;
  }
  .news-card:hover {
    background: #f0f0f0;
    border-left-color: #d33;
  }
  .news-date {
    font-size: 0.8rem;
    color: #666;
    text-transform: uppercase;
    font-weight: bold;
  }
  .news-title {
    font-size: 1.4rem;
    margin: 5px 0;
    font-family: "serif";
  }
  .badge-review {
    background: #d33;
    color: white;
    padding: 2px 8px;
    font-size: 0.7rem;
    border-radius: 3px;
    vertical-align: middle;
  }
</style>

<div class="hero-banner">
  <h1 style="margin:0; letter-spacing: 2px;">OBJNEWS ALPHA</h1>
  <p style="margin:5px 0 0 0; opacity: 0.8;">oo</p>
</div>

<div class="wire-container">
  {% for post in site.posts %}
  <a href="{{ post.url | relative_url }}" class="news-card">
    <div class="news-date">{{ post.date | date: "%B %d, %Y" }}</div>
    <div class="news-title">
      {{ post.title }} 
      {% if post.status == 'review' %}<span class="badge-review">UNDER REVIEW</span>{% endif %}
    </div>
    <p style="margin:0; color: #444;">{{ post.excerpt | strip_html | truncate: 120 }}</p>
  </a>
  {% endfor %}
  
  {% if site.posts.size == 0 %}
  <div class="news-card">
    <div class="news-date">SYSTEM MESSAGE</div>
    <div class="news-title">No articles found in _posts/</div>
    <p>Check your naming convention: YYYY-MM-DD-title.md</p>
  </div>
  {% endif %}
</div>
