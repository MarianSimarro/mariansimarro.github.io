---
layout: page
permalink: /workshops/
title: workshops
description: Workshops and Seminars
nav: false
nav_order: 5
---

## Workshops

  <!-- Display associated workshops -->
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% if project.category == "Workshops" %}
        {% include projects.liquid %}
      {% endif %}
    {% endfor %}
  </div>
