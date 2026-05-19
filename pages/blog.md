---
layout: page
description: Occasional notes and short writing.
permalink: /blog/
---

<div class="post-list">
{% for post in site.posts %}
  <article class="post-row">
    <p class="post-meta"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time></p>
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <p>{{ post.description | default: post.excerpt | strip_html | truncate: 180 }}</p>
  </article>
{% else %}
  <p>No posts yet.</p>
{% endfor %}
</div>
