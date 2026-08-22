---
layout: page
title: Publications
permalink: /publications
---

<style>
  .publications { list-style: none; margin: 0 0 1.5em; padding: 0; }
  .publications li { margin-bottom: 1.5em; padding-bottom: 1.2em; border-bottom: 1px solid #eee; }
  .publications li.pub-highlight {
    border: 1px solid #999;
    padding: 0.8em 1em 0.9em;
  }
  .publications li:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }
  .publications .pub-title { font-size: 1.05em; font-weight: 600; margin: 0 0 0.3em; }
  .publications .pub-title a { text-decoration: none; }
  .publications .pub-title a:hover { text-decoration: underline; }
  .publications .pub-authors { margin: 0 0 0.25em; font-size: 0.88em; }
  .publications .pub-authors a { font-size: inherit; }
  .publications .pub-authors strong { font-weight: 700; }
  .publications .pub-authors sup { font-size: 0.72em; line-height: 0; }
  .publications .pub-authors .pub-orcid { font-size: 0.72em; color: #A6CE39; vertical-align: super; margin-left: 0.1em; }
  .publications .pub-authors .pub-orcid:hover { color: #2b6cb0; }
  .publications .pub-meta { margin: 0; font-size: 0.85em; color: #777; }
  .publications .pub-tags { margin: 0.15em 0 0.35em; }
  .publications .pub-tag {
    display: inline-block;
    margin-right: 0.5em;
    padding: 0.05em 0.6em;
    font-size: 0.72em;
    line-height: 1.5;
    color: #333;
    background: #fff;
    border: 1px solid #999;
    border-radius: 3px;
    letter-spacing: 0.03em;
  }
  .publications li.pub-year-group { border-bottom: none; margin: 1.4em 0 0.6em; padding: 0; }
  .publications li.pub-year-group:first-child { margin-top: 0; }
  .publications li.pub-year-group h2 { font-size: 1.2em; margin: 0; }
  .pub-legend { margin: 0 0 1.2em; font-size: 0.85em; color: #777; }
  .pub-type-icon { margin-right: 6px; font-size: 0.95em; }
  svg.pub-type-icon { vertical-align: -0.125em; }
  .type-journal { color: #2b6cb0; }
  .type-preprint { color: #c05621; }
  .type-conference { color: #2f855a; }
</style>

{%- capture conference_icon -%}<svg class="pub-type-icon type-conference" viewBox="0 0 24 24" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M6 3h12l3 11H3z"/><rect x="10" y="14" width="4" height="6"/><rect x="7" y="20" width="10" height="2"/></svg>{%- endcapture -%}

<p class="pub-legend">
  <i class="pub-type-icon type-journal fa fa-book" aria-hidden="true"></i> Journal article
  &nbsp;&nbsp;&nbsp;
  <i class="pub-type-icon type-preprint fa fa-file-text-o" aria-hidden="true"></i> Preprint
  &nbsp;&nbsp;&nbsp;
  {{ conference_icon }} Conference paper
</p>
<p class="pub-legend"><sup>&dagger;</sup> Co-first author &nbsp;&middot;&nbsp; <sup>&#42;</sup> Corresponding author</p>

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
    <li itemscope itemtype="https://schema.org/ScholarlyArticle"{% if pub.highlight %} class="pub-highlight"{% endif %}>
      <p class="pub-title">
        {% case pub.type %}
          {% when 'journal' %}
            <i class="pub-type-icon type-journal fa fa-book" title="Journal article" aria-hidden="true"></i>
          {% when 'preprint' %}
            <i class="pub-type-icon type-preprint fa fa-file-text-o" title="Preprint" aria-hidden="true"></i>
          {% when 'conference' %}
            {{ conference_icon }}
        {% endcase %}
        <a href="{{ pub.url }}" target="_blank" rel="noopener noreferrer" itemprop="name">{{ pub.title }}</a>
      </p>
      {% if pub.tags %}
      <p class="pub-tags" itemprop="keywords">
        {% for tag in pub.tags %}<span class="pub-tag">{{ tag }}</span>{% endfor %}
      </p>
      {% endif %}
      <p class="pub-authors" itemprop="author">{{ pub.authors | markdownify | remove: '<p>' | remove: '</p>' | strip }}</p>
      <p class="pub-meta">
        {% if pub.venue %}<span itemprop="isPartOf">{{ pub.venue }}{% if pub.year %}, {% endif %}</span>{% endif %}{{ pub.year }}
      </p>
    </li>
  {% endfor %}
</ul>
