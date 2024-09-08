---
layout: default
---

# Welcome to My GitHub Page

Will be writing posts related to Data Engineering and building data pipelines using SQL.

I like playing chess, you can find me at  [chessdotcom](https://www.chess.com/member/nxqplus) or  [lichess](https://lichess.org/@/nxqplus) 

## About Me
* [About Me](about.md)

## Weekly Blog Posts

{% raw %}
{% assign posts_by_year = site.categories.weekly | group_by_exp:"post", "post.date | date: '%Y'" %}

{% for year in posts_by_year %}
  <h3>{{ year.name }}</h3>
  <ul>
    {% for post in year.items %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        - {{ post.date | date: "%B %d, %Y" }}
      </li>
    {% endfor %}
  </ul>
{% endfor %}
{% endraw %}
