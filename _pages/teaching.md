---
layout: page
permalink: /teaching/
title: teaching
description: classes, workshops, and teaching material
nav: false
nav_order: 5
---

## Courses

{% include courses.html past='false' %}

<a data-toggle="collapse" href="#pastCourses" role="button">
    <i class="fas fa-chevron-down"></i> Show Past Courses
</a>

<div class="collapse" id="pastCourses">
      {% include courses.html past='true' %}
</div>
<!--  display the associated projects/cards -->
<div class="projects">

  <!-- Sort projects based on importance -->
  {% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project without using display_categories -->
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% if project.category == "courses" %}
        {% include projects.liquid %}
      {% endif %}
    {% endfor %}
  </div>

</div>

## Workshops

  <!-- Display associated workshops -->
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% if project.category == "Workshops" %}
        {% include projects.liquid %}
      {% endif %}
    {% endfor %}
  </div>
