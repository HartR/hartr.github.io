---
layout: page
title: Projects
description: A small portfolio of technical projects and ongoing experiments.
eyebrow: Workbench
permalink: /projects/
---

<div class="project-grid wide">
{% for project in site.data.projects %}
  <article class="project-card">
    <span>{{ project.tag }}</span>
    <h2>{{ project.name }}</h2>
    <p>{{ project.description }}</p>
    {% if project.link and project.link != '' %}<a href="{{ project.link }}">View source →</a>{% endif %}
  </article>
{% endfor %}
</div>
