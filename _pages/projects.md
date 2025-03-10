---
title: "Projects"
layout: single
permalink: /projects/
---

<style>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  padding: 1rem 0;
}

.project-card {
  border: 1px solid #eaeaea;
  border-radius: 10px;
  overflow: hidden;
  transition: transform 0.3s ease;
}

.project-card:hover {
  transform: translateY(-5px);
}

.project-image img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-bottom: 3px solid #6f777d; /* Tema rengiyle uyumlu */
}

.project-content {
  padding: 1.5rem;
}

.project-tags {
  margin: 1rem 0;
}

@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="projects-grid">
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
          <span class="label">{{ tag }}</span>
        {% endfor %}
      </div>

      <div class="project-links">
        {% if project.github %}
          <a href="https://github.com/{{ project.github }}" class="btn btn--primary">
            <i class="fab fa-github"></i>
          </a>
        {% endif %}
        
        {% if project.demo %}
          <a href="{{ project.demo }}" class="btn btn--success">
            <i class="fas fa-external-link-alt"></i>
          </a>
        {% endif %}
      </div>
    </div>
  </div>
{% endfor %}
</div>
