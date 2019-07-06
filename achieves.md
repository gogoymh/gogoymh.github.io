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
      <div class="achieve-badge">
      <div class="achieve-panel">
        <div class ="achieve-heading">
        <img src="{{ achieve.thumbnail }}" class="achieve-img">
          <h3 href="{{ post_url }}" class="achieve-title">{{ achieve.title }}</h3>
          <p class="achieve-date">{{ achieve_date }}</p>
          <small class="achieve-location">장소 : {{ achieve.location }}</small>
        </div>
      </div>
    </li>
    {% endfor %}
  </ul>
</div>
