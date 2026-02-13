<template>
  <main class="projects">
    <!-- VIDEO BACKGROUND -->
    <video autoplay muted loop playsinline class="bg-video">
      <source src="/src/videos-images/contact.mp4" type="video/mp4" />
    </video>

    <!-- DARK OVERLAY -->
    <div class="overlay"></div>

    <!-- CONTENT -->
    <section class="projects-box">
      <h1 class="animate left delay-1"><span>My</span> Projects</h1>
      <p class="animate left delay-2">
        Here are some of the web applications and websites I've built. Click on each project to view
        more details.
      </p>

      <div class="projects-grid">
        <div
          class="project-card animate bottom"
          v-for="(project, index) in projects"
          :key="project.name"
          :style="{ animationDelay: `${0.3 + index * 0.2}s` }"
        >
          <img :src="project.image" :alt="project.name" />
          <h3>{{ project.name }}</h3>
          <p>{{ project.description }}</p>
          <a :href="project.link" target="_blank" rel="noopener noreferrer" class="btn primary">
            View Project
          </a>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup>
import { ref } from 'vue'

const projects = ref([
  {
    name: 'Aleksandar Travel',
    description:
      'Tourism agency website with destinations, arrangements and gallery. (Site is on Serbian)',
    image: '/videos-images/aleksandartravel.jpg',
    link: 'https://github.com/aleksandar5j/AleksandarTravel',
  },
  {
    name: 'Moj Kuvar - MyCooker',
    description: 'Modern site to find your favorite recipe! (Site is on Serbian)',
    image: '/videos-images/mojkuvar.jpg',
    link: 'https://565q123.e2.mars-hosting.com',
  },
])
</script>

<style scoped>
.projects {
  position: relative;
  min-height: 92.2vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center; /* stavlja sadržaj ka vrhu */
  padding: 30px 20px; /* prostor odozgo */
  color: #e5e7eb;
}

/* VIDEO */
.bg-video {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -2;
  filter: blur(6px);
}

/* OVERLAY */
.overlay {
  position: absolute;
  inset: 0;
  background: rgba(2, 6, 23, 0.75);
  z-index: -1;
}

/* CONTENT */
.projects-box {
  max-width: 1100px;
  width: 100%;
  text-align: center;
  z-index: 1;
}

.projects-box h1 {
  font-size: 42px;
  font-weight: 800;
  margin-bottom: 12px;
  color: #38bdf8;
}

.projects-box h1 span {
  color: white;
}

.projects-box p {
  font-size: 18px;
  color: #cbd5f5;
  margin-bottom: 40px;
}

/* GRID */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 24px;
}

/* PROJECT CARD */
.project-card {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(56, 189, 248, 0.25);
  border-radius: 20px;
  overflow: hidden;
  padding: 20px;
  text-align: center;
  transition: all 0.3s ease;
}

.project-card img {
  width: 100px;
  border-radius: 12px;
  margin-bottom: 16px;
}

.project-card h3 {
  font-size: 20px;
  font-weight: 700;
  margin-bottom: 8px;
}

.project-card p {
  font-size: 16px;
  color: #cbd5f5;
  margin-bottom: 16px;
}

.project-card:hover {
  transform: translateY(-6px);
  border-color: #38bdf8;
  background: rgba(15, 23, 42, 0.95);
}

/* BUTTON */
.btn {
  padding: 12px 24px;
  border-radius: 999px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.25s ease;
}

.btn.primary {
  background-color: #38bdf8;
  color: #020617;
}

.btn.primary:hover {
  background-color: #0ea5e9;
  transform: translateY(-2px);
}

/* ANIMATIONS */
.animate {
  opacity: 0;
  animation: fadeIn 0.8s ease forwards;
}

.left {
  transform: translateX(-60px);
}

.bottom {
  transform: translateY(40px);
}

.delay-1 {
  animation-delay: 0.2s;
}
.delay-2 {
  animation-delay: 0.4s;
}
.delay-3 {
  animation-delay: 0.6s;
}
.delay-4 {
  animation-delay: 0.8s;
}
.delay-5 {
  animation-delay: 1s;
}

@keyframes fadeIn {
  to {
    opacity: 1;
    transform: translate(0, 0);
  }
}
</style>
