---
layout: default
title: Reviews
permalink: /reviews/
---

## Reviews

<table>
    <thead>
        <tr><td>Title</td><td>Rating</td><td>Author</td><td>Date</td></tr>
    </thead>
    <tbody>
    {% for review in site.reviews %}
        <tr><td><a href="{{ review.url | relative_url }}">{{ review.title }} ({{ review.year }})</a></td><td>{{ review.rating }}</td><td>{{ review.author }}</td><td>{{ review.date | date: "%b %d, %Y" }}</td></tr>
    {% endfor %}
    </tbody>
</table>