---
layout: page
title: Youtube
---
<div class="youtube-container">
  <ul class="youtube">
    {% for youtube in site.youtubes reversed %}
    {% assign youtube_date = youtube.date | date: "%Y년 %m월 %d일" %}
    {% capture post_url %} {{ site.baseurl }}{{ youtube.url }} {% endcapture %}
    <li class="youtube-item">
      <div class="youtube-panel">
        <div class ="youtube-heading">
        <div><a href="{{youtube.link}}" target="_blank"><img src="{{ youtube.thumbnail }}" class="youtube-img" alt=""></a></div>
          <h3 href="{{ post_url }}" class="youtube-title">{{ youtube.title }}</h3>
          <p class="youtube-date">{{ youtube_date }}</p>
        </div>
      </div>
    </li>
    {% endfor %}
  </ul>
</div>
