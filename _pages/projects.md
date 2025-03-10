<!-- _pages/projects.md -->

---
layout: single
title: "Projelerim"
permalink: /projects/
author_profile: true
---

{% assign projects = site.data.projects %}

<style>
.project-card {
  display: grid;
  grid-template-columns: 250px 1fr;
  gap: 2rem;
  margin: 2rem 0;
  padding: 1.5rem;
  background: #f8f9fa;
  border-radius: 10px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.project-image img {
  border-radius: 5px;
  height: 200px;
  object-fit: cover;
}

.project-links a { margin-right: 10px; }

@media (max-width: 768px) {
  .project-card { grid-template-columns: 1fr; }
  .project-image img { height: auto; }
}
</style>

{% for project in projects %}
<div class="project-card">
  <div class="project-image">
    <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
  </div>
  
  <div class="project-content">
    <h2>{{ project.title }}</h2>
    <p>{{ project.description }}</p>
    
    <div class="project-tags">
      {% for tag in project.tags %}
        <span class="label label--primary">{{ tag }}</span>
      {% endfor %}
    </div>

    <div class="project-links mt-2">
      {% if project.github %}
        <a href="https://github.com/{{ project.github }}" class="btn btn--github" target="_blank">
          <i class="fab fa-github"></i> GitHub
        </a>
      {% endif %}
      
      {% if project.demo %}
        <a href="{{ project.demo }}" class="btn btn--demo" target="_blank">
          <i class="fas fa-external-link-alt"></i> Demo
        </a>
      {% endif %}
    </div>
  </div>
</div>
{% endfor %}
