---
layout: page
title: Publications
permalink: /publications
---

<style>
  .publications { list-style: none; margin: 0 0 1.5em; padding: 0; }
  .publications li { margin-bottom: 1.5em; padding-bottom: 1.2em; border-bottom: 1px solid #eee; }
  .publications li:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }
  .publications .pub-title { font-size: 1.05em; font-weight: 600; margin: 0 0 0.3em; }
  .publications .pub-title a { text-decoration: none; }
  .publications .pub-title a:hover { text-decoration: underline; }
  .publications .pub-authors { margin: 0 0 0.25em; font-size: 0.92em; }
  .publications .pub-authors strong { font-weight: 700; }
  .publications .pub-meta { margin: 0; font-size: 0.85em; color: #777; }
  .publications li.pub-year-group { border-bottom: none; margin: 1.4em 0 0.6em; padding: 0; }
  .publications li.pub-year-group:first-child { margin-top: 0; }
  .publications li.pub-year-group h2 { font-size: 1.2em; margin: 0; }
</style>

<ul class="publications">
  {% assign previous_year = '' %}
  {% for pub in site.data.publications %}
    {% capture current_year %}{{ pub.year }}{% endcapture %}
    {% if current_year != previous_year %}
      <li class="pub-year-group">
        <h2>{{ current_year }}</h2>
      </li>
      {% assign previous_year = current_year %}
    {% endif %}
    <li itemscope itemtype="https://schema.org/ScholarlyArticle">
      <p class="pub-title">
        <a href="{{ pub.url }}" target="_blank" rel="noopener noreferrer" itemprop="name">{{ pub.title }}</a>
      </p>
      <p class="pub-authors" itemprop="author">{{ pub.authors | markdownify | remove: '<p>' | remove: '</p>' | strip }}</p>
      <p class="pub-meta">
        {% if pub.venue %}<span itemprop="isPartOf">{{ pub.venue }}{% if pub.year %}, {% endif %}</span>{% endif %}{{ pub.year }}
        {% if pub.citations and pub.citations > 0 %}&nbsp;&middot;&nbsp;<span itemprop="citation">Citations: {{ pub.citations }}</span>{% endif %}
      </p>
    </li>
  {% endfor %}
</ul>
