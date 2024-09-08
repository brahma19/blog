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
{% assign weekly_posts = site.posts | where:"post.url contains '.weekly.md'" %}
{% assign posts_by_year = weekly_posts | group_by_year %}

{% if posts_by_year.size == 0 %}
  <p>No weekly posts published yet!</p>
{% else %}
  {% for year in posts_by_year %}
    <h3>{{ year[0].date | date: '%Y' }}</h3>
    <ul>
      {% for post in year %}
        <li>
          <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}
        </li>
      {% endfor %}
    </ul>
  {% endfor %}
{% endif %}
{% endraw %}
