---
layout: default
---

# Welcome to My GitHub Page

Will be writing posts related to Data Engineering and building data pipelines using SQL.

## About Me
* [About Me](about.md)

## Weekly Blog Posts
{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
  <h2>{{ year.name }}</h2>
  {% assign postsByMonth = year.items | group_by_exp:"post", "post.date | date: '%B'" %}
  {% for month in postsByMonth %}
    <h3>{{ month.name }}</h3>
    <ul>
      {% for post in month.items %}
        <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
      {% endfor %}
    </ul>
  {% endfor %}
{% endfor %}
