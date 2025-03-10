<!-- _pages/projects.md (DÜZELTİLMİŞ HALİ) -->

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
  width: 100%; /* Eklendi */
  object-fit: cover;
}

.project-links a { 
  margin-right: 10px;
  margin-bottom: 5px; /* Mobil için */
}

/* Minimal Mistakes Tema Uyumu */
.label--primary {
  background: #6f777d;
  color: white !important;
  padding: 0.2em 0.6em;
  border-radius: 4px;
  font-size: 0.85em;
}

@media (max-width: 768px) {
  .project-card { 
    grid-template-columns: 1fr;
    padding: 1rem; /* Mobil padding düzeltmesi */
  }
  .project-image img { 
    height: 180px; /* Sabit yükseklik korunsun */
  }
}
</style>

{% for project in projects %}
<div class="project-card">
  <div class="project-image">
    <!-- Mutlak path düzeltmesi -->
    <img src="{{ '/' | append: project.image | relative_url }}" alt="{{ project.title }}">
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
        <!-- GitHub URL Format Düzeltmesi -->
        <a href="https://github.com/{{ project.github }}" class="btn btn--info" target="_blank" rel="noopener">
          <i class="fab fa-github"></i> GitHub
        </a>
      {% endif %}
      
      {% if project.demo %}
        <a href="{{ project.demo }}" class="btn btn--success" target="_blank" rel="noopener">
          <i class="fas fa-external-link-alt"></i> Demo
        </a>
      {% endif %}
    </div>
  </div>
</div>
{% endfor %}
