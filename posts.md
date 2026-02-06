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
      {% if post.tag == "Interview" %}
        <strong>[Interview]</strong> 
      {% endif %}
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>