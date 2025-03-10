---
title: "Projects"
layout: single
permalink: /projects/
---

<style>
.projects-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2.5rem;
  padding: 2rem 0;
}

.project-card {
  border: 1px solid #eaeaea;
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  background: white;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.08);
}

.project-image {
  position: relative;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 280px; /* Görsel yüksekliği artırıldı */
  object-fit: cover;
  object-position: top;
  border-bottom: 4px solid #6f777d;
  transition: transform 0.3s ease;
}

.project-image:hover img {
  transform: scale(1.03);
}

.project-content {
  padding: 2rem;
}

.project-content h3 {
  margin: 0 0 1rem;
  font-size: 1.5rem;
  color: #2d3748;
}

.project-content p {
  color: #4a5568;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.tag {
  background: #f7fafc;
  border: 1px solid #e2e8f0;
  color: #2d3748;
  padding: 0.4rem 0.8rem;
  border-radius: 20px;
  font-size: 0.85rem;
}

.project-links {
  display: flex;
  gap: 1rem;
}

@media (max-width: 768px) {
  .projects-container {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .project-image img {
    height: 220px; /* Mobilde biraz küçült */
  }
  
  .project-content {
    padding: 1.5rem;
  }
}
</style>
