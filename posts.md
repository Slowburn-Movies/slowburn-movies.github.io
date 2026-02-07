---
layout: default
title: All Posts
permalink: /posts/
---

<div class="archive-wrapper">
  
  {% for post in site.posts limit: 1 %}
    <section class="hero-post">
      <span class="hero-label">Latest Content</span>
      
      <a href="{{ post.url | relative_url }}">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" class="hero-image" alt="{{ post.title }}">
        {% else %}
          <div class="hero-image" style="background: var(--badge-bg); display: flex; align-items: center; justify-content: center; color: var(--caption-color);">
            [ No Image ]
          </div>
        {% endif %}
      </a>

      <div class="archive-meta" style="margin-bottom: 10px;">
        <span class="type-badge badge-{{ post.type | downcase }}">{{ post.type | capitalize }}</span>
        <span style="color: var(--caption-color); font-size: 0.9rem;">{{ post.date | date: "%B %d, %Y" }}</span>
      </div>

      <h1 class="hero-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h1>

      {% if post.type == "review" and post.rating %}
        <div style="font-size: 1.2rem; color: var(--link-color); margin-top: 0.5rem;">
          ★ {{ post.rating }} / 5
        </div>
      {% endif %}
    </section>
  {% endfor %}

  <hr style="border: 0; border-top: 1px solid var(--badge-bg); margin: 3rem 0;">

  <ul class="editorial-archive">
    {% for post in site.posts offset: 1 %}
      <li class="archive-item">
        
        <div class="archive-date">
          {{ post.date | date: "%b %d %y" }}
        </div>

        <div class="archive-image">
          <a href="{{ post.url | relative_url }}">
            {% if post.image %}
              <img src="{{ post.image | relative_url }}" class="archive-thumb" alt="{{ post.title }}">
            {% else %}
              <div class="archive-thumb-placeholder">.MOV</div>
            {% endif %}
          </a>
        </div>

        <div class="archive-content">
          <h3 class="archive-title">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </h3>
          <div class="archive-meta">
            <span class="type-badge badge-{{ post.type | downcase }}" style="font-size: 0.7rem;">{{ post.type | capitalize }}</span>
            {% if post.type == "review" and post.rating %}
              <span style="font-size: 0.8rem; opacity: 0.8;">★ {{ post.rating }}</span>
            {% endif %}
          </div>
        </div>

      </li>
    {% endfor %}
  </ul>

</div>