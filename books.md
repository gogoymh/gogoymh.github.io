---
layout: page
title: Books
---
<ul class="book">
  {% for book in site.books reversed %}
  {% assign book_date = book.date | date: "%Y년 %m월 %d일" %}
  {% capture post_url %} {{ site.baseurl }}{{ book.url }} {% endcapture %}
  <li class="book-item">
    <div class="book-thumbnail">
      <img src="{{ book.cover-url }}" class="book-img"> 
      <h3 class="book-title">{{ book.title }}</h3>
      <p>{{ book.start-day }} ~ {{ book.end-day }}</p>
    </div>
  </li>
  {% endfor %}
</ul>
