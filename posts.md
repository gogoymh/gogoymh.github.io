---
layout: page
title: Post
---
<div>
  <ul class="posts" style="font-size: 25px">
    {% for post in site.posts %}
      {% assign post_date = post.date | date: "%Y년 %m월 %d일" %}
      {% capture post_url %} {{ site.baseurl }}{{ post.url }} {% endcapture %}
      <li style="font-family: 'Gugi', sans-serif;">
	    <span class="entry-date">{{ post_date }}<br>
	    <a href="{{ post_url }}">{{ post.title | escape }}</a></span>
	    </li>
      <br />
      {% endfor %}
  </ul>
</div>
