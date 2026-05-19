---
layout: page
title: Photo Album
description: Add photos to assets/photos/ and they will appear here automatically.
permalink: /photo-album/
---

{% assign photos = site.static_files | where_exp: "file", "file.path contains '/assets/photos/'" | sort: "path" %}
{% assign image_count = 0 %}
<div class="photo-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if ext == '.jpg' or ext == '.jpeg' or ext == '.png' or ext == '.gif' or ext == '.webp' %}
    {% assign image_count = image_count | plus: 1 %}
    <a class="photo-card" href="{{ photo.path | relative_url }}">
      <img src="{{ photo.path | relative_url }}" alt="Photo {{ image_count }}">
    </a>
  {% endif %}
{% endfor %}
</div>

{% if image_count == 0 %}
<p class="empty-note">No photos yet. Upload image files into <code>assets/photos/</code>, commit them, and this page will display them automatically.</p>
{% endif %}
