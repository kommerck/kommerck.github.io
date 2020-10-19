---
layout: page
title: photos
permalink: /photos/
description: Every now and then I take photos
nav: true
---

<div class="photos">
{% for image in site.static_files %}
  {% if image.path contains 'photos' %}
    <div class="grid-item">
        <a href="{{ site.baseurl }}{{ image.path }}">
          <div class="thumbnail" style="background: url('{{ site.baseurl }}{{ image.path }}'); background-size: 250%; background-position: -160px -140px;">&nbsp;
          </div>
        </a>
    </div>
  {% endif %}
{% endfor %}
</div>
<!-- this is for the lightbox -->
<script type="text/javascript" src="/assets/js/lightbox.js"></script>
<link rel="stylesheet" href="/assets/css/lightbox.css">
