---
layout: single
title: "Projects"
permalink: /projects/
---

## Hello!
Here are my projects!

{% include base_path %}

<style>
  .project-block {
    display: grid;
    grid-template-columns: 300px 1fr;
    gap: 2rem;
    margin-bottom: 3rem;
    padding: 1rem;
    border: 1px solid #eee;
    border-radius: 8px;
  }

  .project-image img {
    width: 100%;
    height: auto;
    border-radius: 4px;
  }

  .project-tags { margin-top: 1rem; }

  @media (max-width: 768px) {
    .project-block { grid-template-columns: 1fr; }
  }
</style>

{% for project in site.data.projects %}
<div class="project-block">
  <div class="project-image">
    <img src="{{ project.image }}" alt="{{ project.title }}">
  </div>
  
  <div class="project-content">
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    
    <div class="project-tags">
      {% for tag in project.tags %}
        <span class="btn btn--primary btn--small">{{ tag }}</span>
      {% endfor %}
    </div>

    {% if project.github_url %}
      <a href="{{ project.github_url }}" class="btn btn--info">
        <i class="fab fa-github"></i> GitHub
      </a>
    {% endif %}
  </div>
</div>
{% endfor %}
