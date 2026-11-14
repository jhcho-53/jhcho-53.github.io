---
layout: page
permalink: /awards/
title: awards
description: Award certificates (click to enlarge). Scholarships are listed in the CV.
nav: true
nav_order: 3
---

<!-- Content lives in _data/awards.yml -->

<style>
  .awards-grid img { width: 100%; aspect-ratio: 5 / 7; object-fit: contain; }
</style>

<div class="row awards-grid">
{% for award in site.data.awards %}
  <div class="col-sm-6 col-md-4 mb-4">
    {% assign award_path = award.image | prepend: "assets/img/awards/" %}
    {% include figure.liquid loading="lazy" path=award_path class="img-fluid rounded z-depth-1" zoomable=true alt=award.title %}
    <div class="mt-2">
      <div class="font-weight-bold">{{ award.title }}</div>
      <div>{{ award.event }}</div>
      {% if award.note %}<div class="text-muted" style="font-size: 0.9rem">{{ award.note }}</div>{% endif %}
      <div class="text-muted" style="font-size: 0.9rem">{{ award.date }}</div>
    </div>
  </div>
{% endfor %}
</div>
