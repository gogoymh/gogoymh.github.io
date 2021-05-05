---
layout: page
title: Youtube
---
<div class="achieve-container">
  <ul class="achieve">
    {% for achieve in site.achieves reversed %}
    {% assign achieve_date = achieve.date | date: "%Y년 %m월 %d일" %}
    {% capture post_url %} {{ site.baseurl }}{{ achieve.url }} {% endcapture %}
    <li class="achieve-item">
      <div class="achieve-panel">
        <div class ="achieve-heading">
        <div><img src="{{ achieve.thumbnail }}" class="achieve-img"></div>
          <h3 href="{{ post_url }}" class="achieve-title">{{ achieve.title }}</h3>
          <p class="achieve-date">{{ achieve_date }}</p>
        </div>
      </div>
    </li>
    {% endfor %}
  </ul>
</div>
