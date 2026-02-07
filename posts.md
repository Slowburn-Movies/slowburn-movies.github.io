---
layout: default
title: All Posts
permalink: /posts/
---

<h2>All Posts</h2>

<div class="filter-bar" style="margin-bottom: 2rem; display: flex; gap: 10px; flex-wrap: wrap;">
  <button class="filter-btn active" onclick="filterType('all')">All</button>
  <button class="filter-btn" onclick="filterType('review')">Reviews</button>
  <button class="filter-btn" onclick="filterType('interview')">Interviews</button>
  <button class="filter-btn" onclick="filterType('news')">News</button>
  <button class="filter-btn" onclick="filterType('event')">Events</button>
</div>

<ul class="editorial-archive" id="post-list">
  {% for post in site.posts %}
    <li class="archive-item" data-type="{{ post.type | downcase }}">
      <div class="archive-date">{{ post.date | date: "%b %d %y" }}</div>
      <div class="archive-image">
        <a href="{{ post.url | relative_url }}">
          {% if post.image %}<img src="{{ post.image | relative_url }}" class="archive-thumb" alt="{{ post.image_alt | default: post.title }}">
          {% elsif post.youtube_id %}<img src="https://img.youtube.com/vi/{{ post.youtube_id }}/hqdefault.jpg" class="archive-thumb" alt="{{ post.title }} video">
          {% else %}<div class="archive-thumb" style="background: var(--badge-bg);"></div>{% endif %}
        </a>
      </div>
      <div class="archive-content">
        <h3 class="archive-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <div class="archive-meta">
          <span class="type-badge badge-{{ post.type | downcase }}" style="font-size: 0.7rem;">{{ post.type | capitalize }}</span>
          {% if post.rating %}<span>★ {{ post.rating }}</span>{% endif %}
        </div>
      </div>
    </li>
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

