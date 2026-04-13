---
layout: default
title: Blog
permalink: /blog/
---
<div class="page-header">
  <h1>Blog</h1>
</div>

<ul class="post-list full">
  {% for post in site.posts %}
  <li class="post-item">
    <a href="{{ post.url }}">
      <div class="post-item-header">
        <span class="post-title">{{ post.title }}</span>
        <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
      </div>
      {% if post.tags and post.tags.size > 0 %}
      <div class="post-tags">
        {% for tag in post.tags %}
        <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
      {% if post.excerpt %}
      <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
      {% endif %}
    </a>
  </li>
  {% endfor %}
</ul>
