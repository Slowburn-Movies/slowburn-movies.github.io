---
layout: default
---

<section class="featured-grid">
  {% assign featured_posts = site.posts | where_not: "hidden", true %}
  {% for post in featured_posts limit: 6 %}
      <a href="{{ post.url | relative_url }}" class="featured-item">
        <div class="featured-image-container">
          {% if post.image %}
            <img src="{{ post.image | relative_url }}" class="featured-image" alt="{{ post.image_alt }}" loading="lazy">
          {% elsif post.youtube_id %}
            <img src="https://img.youtube.com/vi/{{ post.youtube_id }}/maxresdefault.jpg" class="featured-image" alt="{{ post.title }} video" loading="lazy"> 
          {% else %}
            <div class="featured-image" style="background: var(--badge-bg);"></div>
          {% endif %}
        </div>
        
        <span class="type-badge badge-{{ post.type | downcase }}">{{ post.type | capitalize }}</span>
        <h2 class="featured-title">{{ post.title }}</h2>
        
        {% if post.subtitle %}
          <p class="featured-subtitle">{{ post.subtitle }}</p>
        {% endif %}
      </a>
  {% endfor %}
</section>

<div style="text-align: center; margin-top: 2rem;">
  <a href="{{ '/posts/' | relative_url }}" class="filter-btn" style="text-decoration: none; display: inline-block;">View All Posts</a>
</div>

