---
layout: default
title: Projects
permalink: /projects/
---
<div class="page-header">
  <h1>Projects</h1>
</div>

<div id="projects-container">
  {% for project in site.projects %}
  <a href="{{ project.url }}" class="project-card">
    {% if project.image %}
    <img src="{{ project.image }}" alt="{{ project.title }}">
    {% else %}
    <div class="project-card-placeholder"></div>
    {% endif %}
    <div class="project-card-info">
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
      {% assign related = site.posts | where_exp: "post", "post.tags contains project.tag" %}
      {% if related.size > 0 %}
      <span class="post-count">{{ related.size }} post{% if related.size != 1 %}s{% endif %}</span>
      {% endif %}
    </div>
  </a>
  {% endfor %}
</div>
