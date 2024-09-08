---
layout: default
---

# Welcome to My GitHub Page

Will be writing posts related to Data Engineering and building data pipelines using SQL.

I like playing chess, you can find me at  [chessdotcom](https://www.chess.com/member/nxqplus) or  [lichess](https://lichess.org/@/nxqplus) 

## About Me
* [About Me](about.md)

## Weekly Blog Posts

{% raw %}{% for post in site.posts %}
  {% capture year %}{{ post.date | date: "%Y" }}{% endcapture %}
  {% if year != current_year %}
    {% unless forloop.first %}</ul>{% endunless %}
    <h3>{{ year }}</h3>
    <ul>
    {% assign current_year = year %}
  {% endif %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      - {{ post.date | date: "%B %d, %Y" }}
    </li>
  {% if forloop.last %}</ul>{% endif %}
{% endfor %}{% endraw %}
