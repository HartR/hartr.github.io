---
layout: page
title: Blog
description: Notes, tutorials, and field reports from software and systems work.
eyebrow: Writing
permalink: /blog/
---

<div class="archive-list">
{% for post in site.posts %}
  <article class="archive-item">
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %-d, %Y" }}</time>
    <div>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p>{{ post.description | default: post.excerpt | strip_html | truncate: 180 }}</p>
      {% if post.tags %}<p class="tag-row">{% for tag in post.tags %}<span>{{ tag }}</span>{% endfor %}</p>{% endif %}
    </div>
  </article>
{% endfor %}
</div>
