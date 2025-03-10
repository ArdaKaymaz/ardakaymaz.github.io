---
title: "Projects"
layout: single
permalink: /projects/
---

<style>
.projects-grid {
  display: grid;
  gap: 2rem;
}

.project-item {
  display: grid;
  grid-template-columns: 300px 1fr;
  gap: 2rem;
  padding: 1.5rem;
  border: 1px solid #eee;
  border-radius: 8px;
  margin-bottom: 2rem;
}

.project-image {
  position: relative;
  overflow: hidden;
  border-radius: 6px;
}

.project-image img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.project-image:hover img {
  transform: scale(1.05);
}

.project-content h2 {
  margin-top: 0;
  margin-bottom: 1rem;
}

.project-tags {
  margin: 1rem 0;
}

.tag {
  display: inline-block;
  background: #f0f0f0;
  padding: 0.3em 0.8em;
  border-radius: 4px;
  margin: 0.2em;
  font-size: 0.85em;
}

@media (max-width: 768px) {
  .project-item {
    grid-template-columns: 1fr;
  }
  
  .project-image img {
    height: 150px;
  }
}
</style>

<div class="projects-grid">
{% for project in site.projects %}
  <article class="project-item">
    <div class="project-image">
      <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
    </div>
    
    <div class="project-content">
      <h2 class="archive__item-title">{{ project.title }}</h2>
      <p class="archive__item-excerpt">{{ project.excerpt }}</p>
      
      <div class="project-tags">
        {% for tag in project.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>

      <div class="project-links">
        {% if project.github %}
          <a href="https://github.com/{{ project.github }}" class="btn btn--primary" target="_blank">
            <i class="fab fa-github"></i> GitHub
          </a>
        {% endif %}
        
        {% if project.demo %}
          <a href="{{ project.demo }}" class="btn btn--success" target="_blank">
            <i class="fas fa-external-link-alt"></i> Demo
          </a>
        {% endif %}
      </div>
    </div>
  </article>
{% endfor %}
</div>
