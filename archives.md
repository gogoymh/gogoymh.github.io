---
layout: default
permalink: archives/
---
<h1>archives</h1>
<ul>
  {% for archive in year.items %}
    <li>
      <h3>
        <a href="{{ site.baseurl }}{{ post.url }}">
          {{ archive.title }}
          <small>{{ archive.date | date: "%Y년 %m월 %d일" }}</small>
        </a>
      </h3>
    </li>
  {% endfor %}
</ul>
