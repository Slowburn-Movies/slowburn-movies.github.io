---
layout: default
title: Movie Reviews
permalink: /reviews/
---

## Reviews

<table>
    <thead>
        <tr><td>Title</td><td>Year</td><td>Rating</td><td>Author</td></tr>
    </thead>
    <tbody>
    {% for review in site.reviews %}
        <tr><td><a href="{{ review.url | relative_url }}">{{ review.title }}</a></td><td>{{ review.year }}</td><td>{{ review.rating }}</td><td>{{ review.author }}</td></tr>
    {% endfor %}
    </tbody>
</table>