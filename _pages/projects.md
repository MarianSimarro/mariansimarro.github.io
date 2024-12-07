---
layout: page
title: projects
permalink: /projects/
description: Some of the projects I have worked or am curretly working on
nav: true
nav_order: 3
display_categories: [current, past]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
<div id="projects" class="row mt-2 pt-3" style="overflow: visible !important;">
  {% for project in sorted_projects %}
    <div class="project-card">
      {% if project.redirect %}
        <a href="{{ project.redirect }}" target="_blank">
      {% else %}
        <a href="{{ project.url | prepend: site.baseurl }}">
      {% endif %}
        <div class="card">
          <img class="card-img-top" src="{{ project.img | prepend: site.baseurl }}" alt="project thumbnail">
          <div class="card-body">
            <h5 class="card-title text-lowercase">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <div class="row ml-1 mr-1 p-0">
              {% if project.wordpress %}
                <div class="wordpress-icon" data-toggle="tooltip" title="Blog Post">
                  <div class="icon">
                    <a href="{{ project.wordpress }}" target="_blank"><i class="fab fa-wordpress-simple wp-icon"></i></a>
                  </div>
                </div>
              {% endif %}
              {% if project.github %}
                {% assign github_id = project.title | append: project.github | replace: '/', '-' | replace: ' ', '-' %}
                <div class="github-icon">
                  <div class="icon" data-toggle="tooltip" title="Code Repository">
                    <a href="https://github.com/{{ project.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
                  </div>
                  <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                    <i class="fas fa-star"></i>
                    <span id="{{ github_id }}-stars"></span>
                  </span>
                </div>
              {% endif %}
            </div>
          </div>
        </div>
      </a>
    </div>
  {% endfor %}
</div>
