---
layout: default
title: Reviews
permalink: /reviews/
---

## Reviews

<table id="reviews-table">
    <thead>
        <tr>
        <th>Title</th>
        <th>Rating</th>
        <th>Author</th>
        <th>Date</th>
        </tr>
    </thead>
    <tbody>
    {% for review in site.reviews %}
        <tr>
        <td><a href="{{ review.url | relative_url }}">{{ review.title }} ({{ review.year }})</a></td>
        <td>{{ review.rating }}</td>
        <td>{{ review.author }}</td>
        <td data-sort="{{ review.date | date: '%Y%m%d' }}">{{ review.date | date: "%b %d, %Y" }}</td>
        </tr>
    {% endfor %}
    </tbody>
</table>

<style>
    th[role="columnheader"]:not(.no-sort) {
    cursor: pointer;
}

th[role="columnheader"]:after {
    content: ' \2114'; /* Adds a small arrow icon */
    font-size: 0.8em;
    color: #ccc;
}

th[aria-sort="ascending"]:after {
    content: ' \2191'; /* Up arrow */
    color: #000;
}

th[aria-sort="descending"]:after {
    content: ' \2193'; /* Down arrow */
    color: #000;
}
</style>

<script src="https://cdnjs.cloudflare.com/ajax/libs/tablesort/5.2.1/tablesort.min.js"></script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/tablesort/5.2.1/sorts/tablesort.number.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/tablesort/5.2.1/sorts/tablesort.date.min.js"></script>

<script>
  new Tablesort(document.getElementById('reviews-table'));
</script>