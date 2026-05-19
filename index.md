---
layout: default
title: Home
---

<section class="hero single-column">
  <div class="hero-copy">
    <p class="eyebrow">Personal site</p>
    <h1>Practical notes on software, systems, and useful tools.</h1>
    <p class="lead">I’m Hart. This is a small home for occasional technical notes, resume links, and the bits of engineering writing worth keeping around.</p>
    <div class="hero-actions">
      <a class="button primary" href="{{ '/assets/cv.pdf' | relative_url }}">View CV</a>
      <a class="button secondary" href="{{ '/blog/' | relative_url }}">Read the blog</a>
    </div>
  </div>
</section>

<section class="section-grid">
  <div>
    <p class="eyebrow">Writing</p>
    <h2>Latest post</h2>
  </div>
  <div class="post-list">
    {% for post in site.posts limit:1 %}
      <article class="post-card">
        <div class="post-card-meta">{{ post.date | date: "%b %-d, %Y" }}{% if post.categories %} · {{ post.categories | first }}{% endif %}</div>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.description | default: post.excerpt | strip_html | truncate: 140 }}</p>
      </article>
    {% endfor %}
  </div>
</section>
