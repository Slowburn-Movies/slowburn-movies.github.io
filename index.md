---
layout: default
---

<section class="featured-grid">
  {% for post in site.posts limit: 6 %}
    {% unless post.hidden %}
      <a href="{{ post.url | relative_url }}" class="featured-item">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" class="featured-image" alt="{{ post.image_alt }}">
        {% elsif post.youtube_id %}<img src="https://img.youtube.com/vi/{{ post.youtube_id }}/maxresdefault.jpg" class="featured-image" alt="{{ post.title }} video"> 
        {% else %}
          <div class="featured-image" style="background: var(--badge-bg);"></div>
        {% endif %}
        <span class="type-badge badge-{{ post.type | downcase }}">{{ post.type | capitalize }}</span>
        <h2 style="margin: 0.5rem 0; font-size: 1.3rem;">{{ post.title }}</h2>
      </a>
    {% endunless %}
  {% endfor %}
</section>
<!--
<hr style="border: 0; border-top: 1px solid var(--badge-bg); margin-bottom: 2rem;">

<ul class="editorial-archive">
  {% for post in site.posts offset: 3 limit: 7 %}
    {% unless post.hidden %}
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
          <span class="type-badge badge-{{ post.type | downcase }}" style="font-size: 0.7rem;">{{ post.type | capitalize }}</span>
        </div>
      </li>
    {% endunless %}
  {% endfor %}
</ul>
-->
