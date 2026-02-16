---
layout: default
title: Home
---

<section class="featured-grid">
  {% for post in site.posts limit: 3 %}
    {% unless post.hidden %}
      <a href="{{ post.url | relative_url }}" class="featured-item">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" class="featured-image" alt="{{ post.image_alt }}">
        {% elsif post.youtube_id %}<img src="https://img.youtube.com/vi/{{ post.youtube_id }}/maxresdefault.jpg" class="featured-image" alt="{{ post.title }} video"> 
        {% else %}
          <div class="featured-image" style="background: var(--badge-bg);"></div>
        {% endif %}
        <span class="type-badge badge-{{ post.type | downcase }}">{{ post.type | capitalize }}</span>
        <h2 style="margin: 0.5rem 0 0.2rem 0;">{{ post.title }}</h2>
        {% if post.subtitle %}
          <p class="featured-subtitle">{{ post.subtitle }}</p>
        {% endif %}
      </a>
    {% endunless %}
  {% endfor %}
</section>

<hr style="border: 0; border-top: 1px solid var(--badge-bg); margin-bottom: 2rem;">

<div class="filter-bar" style="margin-bottom: 2rem; display: flex; gap: 10px; flex-wrap: wrap;">
  <button class="filter-btn active" onclick="filterType('all')">All</button>
  <button class="filter-btn" onclick="filterType('review')">Reviews</button>
  <button class="filter-btn" onclick="filterType('interview')">Interviews</button>
  <button class="filter-btn" onclick="filterType('news')">News</button>
  <button class="filter-btn" onclick="filterType('event')">Events</button>
  <button class="filter-btn" onclick="filterType('blog')">Blog</button>
</div>

<ul class="editorial-archive">
  {% for post in site.posts offset: 3 %}
    {% unless post.hidden %}
      <li class="archive-item" data-type="{{ post.type | downcase }}">
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
          {% if post.subtitle %}
            <p class="archive-subtitle">{{ post.subtitle }}</p>
          {% endif %}
          <span class="type-badge badge-{{ post.type | downcase }}" style="font-size: 0.7rem;">{{ post.type | capitalize }}</span>
          {% if post.rating %}<span>★ {{ post.rating }}</span>{% endif %}
        </div>
      </li>
    {% endunless %}
  {% endfor %}
</ul>

<script>
function filterType(type) {
  const items = document.querySelectorAll('.archive-item');
  const buttons = document.querySelectorAll('.filter-btn');
  
  // Update button active states
  buttons.forEach(btn => {
    btn.classList.remove('active');
    if(btn.innerText.toLowerCase() === type || (type === 'all' && btn.innerText === 'All')) {
      btn.classList.add('active');
    }
  });

  // Show/Hide items
  items.forEach(item => {
    if (type === 'all' || item.getAttribute('data-type') === type) {
      item.style.display = 'grid'; // Matches your existing CSS display
    } else {
      item.style.display = 'none';
    }
  });
}
</script>
