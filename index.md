---
layout: default
---

## Latest Articles
<ul>
  {% for post in site.posts %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

<hr>

## My Reviews
<ul>
  {% for review in site.reviews %}
    <li>
      <a href="{{ review.url }}">{{ review.title }}</a> 
      — <strong>Rating: {{ review.rating }}/5</strong>
    </li>
  {% endfor %}
</ul>
