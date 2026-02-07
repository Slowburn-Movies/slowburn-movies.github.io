---
layout: default
---

## Latest 

<ul>
  {% for item in site.posts limit: 5 %}
    <li style="display: flex; align-items: center; gap: 15px; margin-bottom: 20px;">
      
      {% if item.image %}
        <img src="{{ item.image | relative_url }}" 
             alt="{{ item.title }}" 
             style="width: 60px; height: 60px; object-fit: cover; border-radius: 4px;">
      {% else %}
        <div style="width: 60px; height: 60px; background: var(--bg-color); border-radius: 4px;"></div>
      {% endif %}

      <div>
        <span class="type-tag" style="font-size: 0.8rem; text-transform: uppercase;">{{ item.type }}</span>
        <h3 style="margin: 0;"><a href="{{ item.url | relative_url }}">{{ item.title }}</a></h3>
        {% if item.type == "review" %}
          <span>{{ item.rating }} / 5 ★ </span>
        {% endif %}
      </div>

    </li>
  {% endfor %}
</ul>
