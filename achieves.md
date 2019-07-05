---
layout: page
title: Achieves
---
<div>
  <ul class="archieves">
    {% for achieve in site.achieves reversed %}
      {% assign achieve_date = achieve.date | date: "%Y년 %m월 %d일" %}
      {% capture post_url %} {{ site.baseurl }}{{ achieve.url }} {% endcapture %}
      <li style="font-family: 'Gugi', sans-serif;">
	    <span class="entry-date">{{ achieve_date }}<br>
	    <a href="{{ post_url }}">{{ achieve.title }}</a></span>
	    </li>
      <br />
      {% endfor %}
  </ul>
</div>
