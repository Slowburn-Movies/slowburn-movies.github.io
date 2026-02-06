---
layout: default
---

## Latest Articles
<ul>
  {% for post in site.posts limit: 3 %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

<hr>

## My Reviews
<ul>
  {% assign latest_reviews = site.reviews | reverse %}
  {% for review in latest_reviews limit: 3 %}
    <li>
      <a href="{{ review.url }}">{{ review.title }}</a> 
      — <strong>Rating: {{ review.rating }}/5</strong>
    </li>
  {% endfor %}
</ul>
