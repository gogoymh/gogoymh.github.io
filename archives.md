---
layout: page
title: Archives
---

<h2>All Posts</h2>
<div>
  <ul class="posts">
    {% for post in site.posts %}
    {% assign post_date = post.date | date_to_string %}
    {% capture post_url %} {{ site.baseurl }}{{ post.url }} {% endcapture %}
    <li>
      <span class="entry-date">{{ post_date | date: "%Y년 %m월 %d일" }}<br>
      <a href="{{ post_url }}">{{ post.title }}</a></span>
	 </li>
    {% endfor %}
  </ul>
</div>
