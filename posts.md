---
layout: default
title: Posts
permalink: /posts/
---

## Posts

<ul>
  {% for post in site.posts %}
    <li>
      <span style="color: #888;">{{ post.date | date: "%b %d, %Y" }}</span> — 
      {% if post.type %}
        <span class="type-badge">{{ item.type }}</span> 
      {% endif %}
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>