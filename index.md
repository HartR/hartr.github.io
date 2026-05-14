---
layout: default
title: Home
---

<section class="hero">
  <div class="hero-copy">
    <p class="eyebrow">Personal engineering blog</p>
    <h1>Practical notes on software, systems, and projects.</h1>
    <p class="lead">A polished home for writeups about infrastructure, automation, Linux, debugging, hardware projects, and the small tools that make technical work more reliable.</p>
    <div class="hero-actions">
      <a class="button primary" href="{{ '/blog/' | relative_url }}">Read the blog</a>
      <a class="button secondary" href="{{ '/projects/' | relative_url }}">See projects</a>
    </div>
  </div>
  <aside class="hero-card">
    <span class="status-dot"></span>
    <h2>Currently writing about</h2>
    <ul>
      <li>Unix automation and recovery playbooks</li>
      <li>Self-hosted infrastructure</li>
      <li>Practical hardware experiments</li>
    </ul>
  </aside>
</section>

<section class="section-grid">
  <div>
    <p class="eyebrow">Latest writing</p>
    <h2>Recent posts</h2>
  </div>
  <div class="post-list">
    {% for post in site.posts limit:3 %}
      <article class="post-card">
        <div class="post-card-meta">{{ post.date | date: "%b %-d, %Y" }}{% if post.categories %} · {{ post.categories | first }}{% endif %}</div>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.description | default: post.excerpt | strip_html | truncate: 140 }}</p>
      </article>
    {% endfor %}
  </div>
</section>

<section class="section-grid accent-section">
  <div>
    <p class="eyebrow">Selected work</p>
    <h2>Projects</h2>
  </div>
  <div class="project-grid">
    {% for project in site.data.projects %}
      <article class="project-card">
        <span>{{ project.tag }}</span>
        <h3>{{ project.name }}</h3>
        <p>{{ project.description }}</p>
        {% if project.link and project.link != '' %}<a href="{{ project.link }}">View source →</a>{% endif %}
      </article>
    {% endfor %}
  </div>
</section>
