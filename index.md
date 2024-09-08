---
layout: default
---

# Welcome to My GitHub Page

Will be writing posts related to Data Engineering and building data pipelines using SQL.

I like playing chess, you can find me at  [chessdotcom](https://www.chess.com/member/nxqplus) or  [lichess](https://lichess.org/@/nxqplus) 

## About Me
* [About Me](about.md)

## Weekly Blog Posts
* [2024-08-31](_posts/2024-08-31-weekly.md)
* [2024-09-07](_posts/2024-09-07-weekly.md)

{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'"  %}
{% for year in postsByYear %}
  <h3>{{ year.name }}</h3>
  <ul>
    {% for post in year.items %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
