---
title: "Projelerim"
layout: single
permalink: /projects/
---

<style>
  .project-card {
    border: 1px solid #eaeaea;
    padding: 1.5rem;
    margin-bottom: 2rem;
    border-radius: 8px;
  }
  .project-links a {
    margin-right: 1rem;
  }
</style>

{% for project in site.projects %}
  <div class="project-card">
    <h2>{{ project.title }}</h2>
    <p>{{ project.excerpt }}</p>
    
    <div class="project-tags">
      {% for tag in project.tags %}
        <span class="tag">{{ tag }}</span>
      {% endfor %}
    </div>

    <div class="project-links">
      <a href="{{ project.github }}" class="btn" target="_blank">
        <i class="fab fa-github"></i> GitHub
      </a>
      {% if project.demo %}
        <a href="{{ project.demo }}" class="btn" target="_blank">
          <i class="fas fa-external-link-alt"></i> Demo
        </a>
      {% endif %}
    </div>
  </div>
{% endfor %}
