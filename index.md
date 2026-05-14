---
layout: default
title: Home
---

# Welcome to my site
This is a simple Jekyll site hosted on GitHub Pages at the root domain.

## Projects
{% for project in site.data.projects %}
### {{ project.name }} [{{ project.tag }}]
{{ project.description }}
{% if project.link %}[View Source]({{ project.link }}){% endif %}
{% endfor %}

[View my updated CV](/assets/cv.pdf)
