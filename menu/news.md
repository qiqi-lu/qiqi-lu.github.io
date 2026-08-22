---
layout: page
title: News
permalink: /news
description: "News and updates from Qiqi Lu, Ph.D. candidate at Southern Medical University."
---

<style>
  .news { list-style: none; margin: 0 0 1.5em; padding: 0; }
  .news li { display: flex; align-items: flex-start; margin-bottom: 1.2em; padding-bottom: 1em; border-bottom: 1px solid #f0f0f0; }
  .news li:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }
  .news .news-date { flex: 0 0 6em; font-size: 0.78em; color: #888; font-variant-numeric: tabular-nums; padding-top: 0.15em; }
  .news .news-body { flex: 1 1 auto; min-width: 0; }
  .news .news-title { line-height: 1.5; }
  .news .news-title a { text-decoration: none; }
  .news .news-title a:hover { text-decoration: underline; }
  .news .news-content { margin-top: 0.25em; color: #555; font-size: 0.9em; }
</style>

{% assign news = site.data.news %}
{% if news.size > 0 %}
  <ul class="news">
    {% for item in news %}
      <li itemscope>
        {% if item.date %}<span class="news-date">{{ item.date }}</span>{% endif %}
        <div class="news-body">
          <span class="news-title">
            {% if item.url %}<a href="{{ item.url }}" target="_blank" rel="noopener noreferrer">{{ item.title | markdownify | remove: '<p>' | remove: '</p>' | strip }}</a>
            {% else %}{{ item.title | markdownify | remove: '<p>' | remove: '</p>' | strip }}{% endif %}
          </span>
          {% if item.content %}<div class="news-content">{{ item.content | markdownify | remove: '<p>' | remove: '</p>' | strip }}</div>{% endif %}
        </div>
      </li>
    {% endfor %}
  </ul>
{% else %}
  <p>No news yet.</p>
{% endif %}
