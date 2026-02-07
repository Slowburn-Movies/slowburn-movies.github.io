---
layout: default
---

## Latest 

<ul class="post-list">
  {% for item in site.posts limit: 5 %}
    <li class="post-item">
      
      {% if item.image %}
        <img src="{{ item.image | relative_url }}" alt="{{ item.title }}" class="list-thumb">
      {% else %}
        <div class="list-thumb" style="background: var(--badge-bg);"></div>
      {% endif %}

      <div class="post-info">
        <div style="margin-bottom: 4px;">
          <span class="type-badge badge-{{ item.type | downcase }}">{{ item.type | capitalize }}</span>
          {% if item.type == "review" and item.rating %}
            <span style="font-size: 0.9rem; opacity: 0.8;">{{ item.rating }} / 5 ★ </span>
          {% endif %}
        </div>
        
        <h3 style="margin: 0; font-size: 1.2rem;">
          <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
        </h3>
        
        <small style="opacity: 0.7;">{{ item.date | date: "%b %d, %Y" }}</small>
      </div>

    </li>
  {% endfor %}
</ul>
