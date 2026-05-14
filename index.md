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

## Recent Posts
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> — {{ post.date | date_to_string }}
    </li>
  {% endfor %}
</ul>

[View my updated CV](/assets/cv.pdf)
