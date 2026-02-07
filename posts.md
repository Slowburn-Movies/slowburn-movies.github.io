---
layout: default
title: All Posts
permalink: /posts/
---

<h2>All Posts</h2>

<ul class="editorial-archive">
  {% for post in site.posts %}
    <li class="archive-item">
      <div class="archive-date">{{ post.date | date: "%b %d %y" }}</div>
      <div class="archive-image">
        <a href="{{ post.url | relative_url }}">
          {% if post.image %}<img src="{{ post.image | relative_url }}" class="archive-thumb" alt="{{ post.image_alt }}">
          {% elsif post.youtube_id %}<img src="https://img.youtube.com/vi/{{ post.youtube_id }}/hqdefault.jpg" class="archive-thumb" alt="{{ post.title }} video">
          {% else %}<div class="archive-thumb" style="background: var(--badge-bg);"></div>{% endif %}
        </a>
      </div>
      <div class="archive-content">
        <h3 class="archive-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <div class="archive-meta">
          <span class="type-badge badge-{{ post.type | downcase }}" style="font-size: 0.7rem;">{{ post.type | capitalize }}</span>
          {% if post.rating %}<span>★ {{ post.rating }}</span>{% endif %}
        </div>
      </div>
    </li>
  {% endfor %}
</ul>