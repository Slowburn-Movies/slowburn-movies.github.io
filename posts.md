---
layout: default
title: All Posts
permalink: /posts/
---

## All Posts

<ul>
  {% for post in site.posts %}
    <li>
      <span style="color: var(--caption-color);">{{ post.date | date: "%b %d, %Y" }}</span> — 
      {% if post.type %}
        <span class="type-badge badge-{{ item.type | downcase }}">{{ post.type | capitalize }}</span> 
      {% endif %}
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>