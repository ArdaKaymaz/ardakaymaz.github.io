---
title: "Publications"
layout: splash
permalink: /publications/
---

<style>
.publications-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  padding: 1rem 0;
}

.publication-card {
  border: 1px solid #eaeaea;
  border-radius: 8px;
  overflow: hidden;
  transition: transform 0.2s;
  padding: 0rem;
  margin-bottom: 0rem;
}

.publication-card:hover {
  transform: translateY(-3px);
}

.publication-image {
  position: relative;
  width: 100%;
  height: 250px;
  overflow: hidden;
  border-radius: 8px 8px 0 0;
}

.publication-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  border-bottom: 1px solid #6f777d;
  margin-bottom: 0rem;
}

.publication-content {
  padding: 0.5rem;
}

.publication-content h2 {
  margin-top: 0rem !important;
  padding-top: 0rem;
}

@media (max-width: 768px) {
  .publications-container {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="publications-container">
{% for publication in site.publications %}
  <div class="publication-card">
    <div class="publication-image">
      <img src="{{ publication.image | relative_url }}" alt="{{ publication.title }}">
    </div>
    
    <div class="publication-content">
      <h2>{{ publication.title }}</h2>
      <p>{{ publication.excerpt }}</p>
      
      <div class="publication-tags">
        {% for tag in publication.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>

      <div class="github-links">
        {% if publication.github %}
          <a href="https://github.com/{{ publication.github }}" class="btn btn--primary">
            <i class="fab fa-github"></i> GitHub
          </a>
        {% endif %}

        {% if publication.paper %}
          <a href="{{ publication.paper }}" class="btn btn--primary">
            <i class="fas fa-external-link-alt"></i> Paper Link
          </a>
        {% endif %}
        
        {% if publication.app %}
          <a href="{{ publication.app }}" class="btn btn--success">
            <i class="fas fa-external-link-alt"></i> App Link
          </a>
        {% endif %}
      </div>
    </div>
  </div>
{% endfor %}
</div>
