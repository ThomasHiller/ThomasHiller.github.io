---
layout: single
title: "Photography"
permalink: /photography/
author_profile: true

photos:

    # resolution 1200 x 1200 px, 200-500 KB
  - category: "Bat portraits"
    file: "Artibeus.jamaicensis.jpg"
    title: "Jamaican fruit-eating bat"
    species: "Artibeus jamaicensis"
    location: "Piedras Blancas, Costa Rica"
    alt: ""

  - category: "Bat portraits"
    file: "Carollia.perspicillata.jpg"
    title: "Seba's short-tailed bat"
    species: "Carollia perspicillata"
    location: "Parque Nacional Piedras Blancas, Costa Rica"
    alt: ""

  #- category: "Landscapes"
  #  file: "landscape-01.jpg"
  #  title: "Forest at sunset"
  #  location: "Location, country"
  #  alt: "Forest canopy photographed at sunset"
---

<style>
.photo-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(220px, 100%), 1fr));
  gap: 24px;
  margin-bottom: 32px;
}

.photo-gallery figure {
  margin: 0;
  min-width: 0;
}

.photo-gallery img {
  display: block;
  width: 100%;
  height: auto;
}

.photo-gallery figcaption {
  margin-top: 8px;
  font-size: 0.8em;
  line-height: 1.5;
}
</style>

{% assign categories = page.photos | group_by: "category" %}

{% for category in categories %}
<h2>{{ category.name | escape }}</h2>

<div class="photo-gallery">
  {% for photo in category.items %}
  {% assign image_url = '/images/photography/' | append: photo.file | relative_url %}

  <figure>
    <a href="{{ image_url }}">
      <img src="{{ image_url }}"
           alt="{{ photo.alt | escape }}"
           loading="lazy">
    </a>
    <figcaption>
      {{ photo.title | escape }}
      {% if photo.species %}
      — <em>{{ photo.species | escape }}</em>
      {% endif %}
      <br>
      {{ photo.location | escape }}
    </figcaption>
  </figure>

  {% endfor %}
</div>

{% endfor %}

<hr>
<p><small>
  Photographs © Thomas Hiller, unless otherwise credited.
  All rights reserved. Please contact me for permission to reuse.
</small></p>