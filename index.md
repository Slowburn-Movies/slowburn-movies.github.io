---
layout: default
---

## Latest 

<ul>
  {% comment %} Join the two collections into one array {% endcomment %}
  {% assign combined_items = site.posts | concat: site.reviews %}
  
  {% comment %} Sort them by date (newest first) and limit to 5 {% endcomment %}
  {% assign sorted_items = combined_items | sort: 'date' | reverse %}

  {% for item in sorted_items limit: 5 %}
    <li>
      <span style="color: var(--caption-color);">{{ item.date | date: "%b %d" }}</span> — 
      
      <span class="type-badge">{{ item.type }}</span>
      
      <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
    </li>
  {% endfor %}
</ul>
