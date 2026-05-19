---
layout: default
title: Home
---

<section class="home-intro">
  <h1>{{ site.title }}</h1>
  <p class="subtitle">{{ site.subtitle }}</p>
  <p class="about-blurb">I’m Hart. This is a small personal site for occasional notes, a simple photo album, and my CV.</p>
</section>

<section class="latest-post">
  <h2>Latest post</h2>
  {% for post in site.posts limit:1 %}
    <article class="post-preview">
      <p class="post-meta"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time></p>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p>{{ post.description | default: post.excerpt | strip_html | truncate: 180 }}</p>
    </article>
  {% else %}
    <p>No posts yet.</p>
  {% endfor %}
</section>
