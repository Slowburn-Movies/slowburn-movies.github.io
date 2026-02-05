<h2>Latest Reviews</h2>
{% for post in site.categories.reviews limit:3 %}
  <a href="{{ post.url }}">{{ post.title }}</a><br>
{% endfor %}

<h2>Latest News</h2>
{% for post in site.categories.news limit:3 %}
  <a href="{{ post.url }}">{{ post.title }}</a><br>
{% endfor %}
