---
title: "Projects"
layout: single
permalink: /projects/
---

<style>
.projects-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
}

.project-card {
  border: 1px solid #eee;
  border-radius: 8px;
  overflow: hidden;
  display: flex;
  flex-direction: column; /* İçeriği dikey hizala */
}

.project-image {
  position: relative;
  width: 100%;
  padding-top: 56.25%; /* 16:9 aspect ratio (height/width*100) */
}

.project-image img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover; /* Görseli kapsayıcıya sığdır */
}

.project-content {
  padding: 1rem;
  flex-grow: 1; /* İçerik alanını esnek yap */
}

/* Diğer stiller aynı kalabilir */
</style>
