---
layout: default
title: News
permalink: /news/
---

# News

<ul>
  {% for post in site.posts %}
    <li>
      <span style="color: #888;">{{ post.date | date: "%b %d, %Y" }}</span> — 
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>