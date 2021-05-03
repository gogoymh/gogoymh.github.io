---
layout: page
title: Pubilcations
---
<div class="publication-container">
  <ul class="publication">
    {% for publication in site.publications reversed %}
    {% assign publication_date = pulication.date | date: "%Y년 %m월 %d일" %}
    {% capture post_url %} {{ site.baseurl }}{{ publication.url }} {% endcapture %}
    <li class="publication-item">
      <div class="publication-panel">
        <div class ="publication-heading">
        <div><img src="{{ publication.thumbnail }}" class="publication-img"></div>
          <h3 href="{{ post_url }}" class="publication-title">{{ publication.title }}</h3>
          <p class="publication-date">{{ publication_date }}</p>
          <hr class="publication-divider"/>
          <div class="publication-info">
            <p class="publication-where">저널/학회 : {{ publication.where }}</p>
            <p class ="publication-team">분야(키워드) : {{ publication.field }}({{ publication.keywords }})</p>
          </div>
        </div>
      </div>
    </li>
    {% endfor %}
  </ul>
</div>
