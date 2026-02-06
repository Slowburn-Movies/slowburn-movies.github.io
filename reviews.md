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

/* Default state: show a neutral double arrow */
th[role="columnheader"]:after {
    content: " ↕";
    font-size: 0.8em;
    opacity: 0.3;
}

/* Sorted Ascending: Up arrow */
th[aria-sort="ascending"]:after {
    content: " ↑";
    opacity: 1;
}

/* Sorted Descending: Down arrow */
th[aria-sort="descending"]:after {
    content: " ↓";
    opacity: 1;
}
</style>

<script src="https://cdnjs.cloudflare.com/ajax/libs/tablesort/5.2.1/tablesort.min.js"></script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/tablesort/5.2.1/sorts/tablesort.number.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/tablesort/5.2.1/sorts/tablesort.date.min.js"></script>

<script>
  new Tablesort(document.getElementById('reviews-table'));
</script>