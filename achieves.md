---
layout: page
title: Achieves
---
<div class="achieve-container">
  <ul class="achieve">
    {% for achieve in site.achieves reversed %}
    {% assign achieve_date = achieve.date | date: "%Y년 %m월 %d일" %}
    {% capture post_url %} {{ site.baseurl }}{{ achieve.url }} {% endcapture %}
    <li class="achieve-item">
      <div class="achieve-panel">
        <div class ="achieve-heading">
          <a  href="{{ post_url }}" class="achieve-title">{{ achieve.title }}</a>
          <p class="achieve-date">{{ achieve_date }}</p>
        </div>
        <div class="achieve-body">
          <img src="{{ achieve.thumbnail }}" class="achieve-img">
          <p>{{ achieve.content }}</p>
        </div>
      </div>
    </li>
    {% endfor %}
  </ul>
</div>
