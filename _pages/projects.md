---
title: "Projects"
layout: single
permalink: /projects/
---

<style>
.projects-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr); /* 2 sütun */
  gap: 2rem;
  padding: 1rem 0;
}

.project-card {
  border: 1px solid #eaeaea;
  border-radius: 8px;
  overflow: hidden;
  transition: transform 0.2s;
}

.project-card:hover {
  transform: translateY(-3px);
}

.project-image img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-bottom: 2px solid #6f777d;
}

.project-content {
  padding: 1.5rem;
}

@media (max-width: 768px) {
  .projects-container {
    grid-template-columns: 1fr; /* Mobilde tek sütun */
  }
}
</style>

<div class="projects-container">
{% for project in site.projects %}
  <div class="project-card">
    <div class="project-image">
      <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
    </div>
    
    <div class="project-content">
      <h3>{{ project.title }}</h3>
      <p>{{ project.excerpt }}</p>
      
      <div class="project-tags">
        {% for tag in project.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>

      <div class="project-links">
        {% if project.github %}
          <a href="https://github.com/{{ project.github }}" class="btn btn--primary">
            <i class="fab fa-github"></i> GitHub
          </a>
        {% endif %}
        
        {% if project.demo %}
          <a href="{{ project.demo }}" class="btn btn--success">
            <i class="fas fa-external-link-alt"></i> Demo
          </a>
        {% endif %}
      </div>
    </div>
  </div>
{% endfor %}
</div>
