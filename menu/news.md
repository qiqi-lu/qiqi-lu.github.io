---
layout: page
title: News
permalink: /news
---

<style>
  .news { list-style: none; margin: 0 0 1.5em; padding: 0; }
  .news li { margin-bottom: 1.2em; padding-bottom: 1em; border-bottom: 1px solid #eee; }
  .news li:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }
  .news .news-date { display: inline-block; font-size: 0.85em; color: #777; margin-right: 0.6em; }
  .news .news-title a { text-decoration: none; }
  .news .news-title a:hover { text-decoration: underline; }
</style>

{% if site.data.news.size > 0 %}
  <ul class="news">
    {% for item in site.data.news %}
      <li itemscope>
        {% if item.date %}<span class="news-date">{{ item.date | date: "%Y-%m-%d" }}</span>{% endif %}
        <span class="news-title">
          {% if item.url %}<a href="{{ item.url }}" target="_blank" rel="noopener noreferrer">{{ item.title }}</a>
          {% else %}{{ item.title }}{% endif %}
        </span>
      </li>
    {% endfor %}
  </ul>
{% else %}
  <p>No news yet.</p>
{% endif %}
