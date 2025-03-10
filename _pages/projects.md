---
title: "Projects"
layout: single
permalink: /projects/
---

<style>
.projects-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem; /* Container genel boşluğu azaltıldı */
}

.project-card {
  border: 1px solid #eee;
  border-radius: 8px;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 180px; /* Görsel yüksekliği azaltıldı */
  object-fit: cover;
}

.project-content {
  padding: 1rem; /* Padding daraltıldı */
}

.project-content h3 {
  margin: 0.5rem 0; /* Başlık boşluğu ayarlandı */
}

.project-content p {
  margin: 0.3rem 0 0.8rem; /* Açıklama boşlukları optimize edildi */
}

.project-tags {
  margin: 0.5rem 0;
}

@media (max-width: 768px) {
  .projects-container {
    gap: 1rem;
  }
  
  .project-content {
    padding: 0.8rem;
  }
}
</style>
