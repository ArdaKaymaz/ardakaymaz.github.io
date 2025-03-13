---
title: "Publications"
layout: splash
permalink: /publications/
---

<style>
.projects-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  padding: 1rem 0;
}

.project-card {
  border: 1px solid #eaeaea;
  border-radius: 8px;
  overflow: hidden;
  transition: transform 0.2s;
  padding: 0rem;
  margin-bottom: 0rem;
}

.project-card:hover {
  transform: translateY(-3px);
}

.project-image {
  position: relative;
  width: 100%;
  height: 250px;
  overflow: hidden;
  border-radius: 8px 8px 0 0;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  border-bottom: 1px solid #6f777d;
  margin-bottom: 0rem;
}

.project-content {
  padding: 0.5rem;
}

.project-content h2 {
  margin-top: 0rem !important;
  padding-top: 0rem;
}

@media (max-width: 768px) {
  .projects-container {
    grid-template-columns: 1fr;
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
      <h2>{{ project.title }}</h2>
      <p>{{ project.excerpt }}</p>
      
      <div class="project-tags">
        {% for tag in project.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>

      <div class="github-links">
        {% if project.github %}
          <a href="https://github.com/{{ project.github }}" class="btn btn--primary">
            <i class="fab fa-github"></i> GitHub
          </a>
        {% endif %}

        {% if project.paper %}
          <a href="{{ project.paper }}" class="btn btn--primary">
            <i class="fas fa-external-link-alt"></i> Paper Link
          </a>
        {% endif %}
        
        {% if project.app %}
          <a href="{{ project.app }}" class="btn btn--success">
            <i class="fas fa-external-link-alt"></i> App Link
          </a>
        {% endif %}
      </div>
    </div>
  </div>
{% endfor %}
</div>
