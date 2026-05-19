---
layout: default
title: Home
---

<section class="home-intro">
  <h2 class="about-blurb">Hi, I’m Hart. This is my only social media.</h2>
</section>

<section class="latest-post">
  <h2>Latest post</h2>

  {% assign latest_post = site.posts.first %}
  {% if latest_post %}
    <p>
      <a href="{{ latest_post.url | relative_url }}">{{ latest_post.title }}</a>
    </p>
    <p>{{ latest_post.excerpt | strip_html | truncate: 160 }}</p>
  {% endif %}
</section>
