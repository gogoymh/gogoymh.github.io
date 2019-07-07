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
        <div><img src="{{ achieve.thumbnail }}" class="achieve-img"></div>
          <h3 href="{{ post_url }}" class="achieve-title">{{ achieve.title }}</h3>
          <p class="achieve-date">{{ achieve_date }}</p>
          <hr class="achieve-divider"/>
          <div class="achieve-info">
            <p class="achieve-location">장소 : {{ achieve.location }}</p>
            <p class ="achieve-team">팀명(멤버) : {{ achieve.teamname }}({{ achieve.member }})</p>
          </div>
        </div>
      </div>
    </li>
    {% endfor %}
  </ul>
</div>
