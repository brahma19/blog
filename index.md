---
layout: default
---

# Welcome to My GitHub Page

Will be writing posts related to Data Engineering and building data pipelines using SQL.

I like playing chess, you can find me at  [chessdotcom](https://www.chess.com/member/nxqplus) or  [lichess](https://lichess.org/@/nxqplus) 

## About Me
* [About Me](about.md)

## Weekly Blog Posts
{% for post in site.categories.weekly %}
  {% assign currentdate = post.date | date: "%Y" %}
  {% if currentdate != date %}
    {% unless forloop.first %}</ul>{% endunless %}
    <h3 id="y{{post.date | date: "%Y"}}">{{ currentdate }}</h3>
    <ul>
    {% assign date = currentdate %}
  {% endif %}
    <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}</li>
  {% if forloop.last %}</ul>{% endif %}
{% endfor %}
