---
layout: default
title: Home
---

<section class="home-intro">
  <p class="about-blurb">Hi, I’m Hart. This is my only social media.</p>
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
