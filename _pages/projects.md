---
layout: page
title: photos
permalink: /photos/
description: A collection of memorable photos.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

<div class="photos">
  {% assign all_photos = site.data.photos %}
  {% for photo_set in all_photos %}
    <div class="photo-set">
      <h2 class="photo-title">{{ photo_set.title }}</h2>
      <p class="photo-description">{{ photo_set.description }}</p>
      <div class="photo-images">
        {% for photo in photo_set.photos %}
          <img src="{{ photo }}" alt="{{ photo_set.title }}" class="photo-img">
        {% endfor %}
      </div>
    </div>
  {% endfor %}
</div>