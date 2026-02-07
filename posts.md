---
layout: default
title: All Posts
permalink: /posts/
---

## All Posts

<div class="archive-wrapper">
  
  {% for post in site.posts limit: 1 %}
    <section class="hero-post" style="margin-bottom: 3rem;">
      <h2 style="text-transform: uppercase; font-size: 0.8rem; letter-spacing: 1px; opacity: 0.6;">Latest</h2>
      {% if post.image %}
        <img src="{{ post.image | relative_url }}" class="post-featured-image" style="width: 100%; height: 300px; object-fit: cover; border-radius: 4px;">
      {% endif %}
      <h1 class="hero-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h1>
      <div class="archive-meta">
        <span class="type-badge badge-{{ post.type | downcase }}">{{ post.type }}</span>
        <span style="color: var(--caption-color);">{{ post.date | date: "%B %d, %Y" }}</span>
      </div>
    </section>
  {% endfor %}

  <hr style="border: 0; border-top: 1px solid var(--badge-bg); margin: 2rem 0;">

  <ul class="editorial-archive">
    {% for post in site.posts offset: 1 %}
      <li class="archive-item">
        <div class="archive-date">
          {{ post.date | date: "%b %d %y" }}
        </div>
        <div class="archive-content">
          <h3 class="archive-title">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </h3>
          <div class="archive-meta">
            <span class="type-badge badge-{{ post.type | downcase }}" style="font-size: 0.7rem;">{{ post.type }}</span>
            {% if post.type == "review" and post.rating %}
              <span style="font-size: 0.8rem; opacity: 0.8;">★ {{ post.rating }}</span>
            {% endif %}
          </div>
        </div>
      </li>
    {% endfor %}
  </ul>
</div>