<template>
  <main class="skills">
    <!-- VIDEO BACKGROUND -->
    <video autoplay muted loop playsinline class="bg-video">
      <source src="/src/videos-images/skills.mp4" type="video/mp4" />
    </video>

    <!-- DARK OVERLAY -->
    <div class="overlay"></div>

    <!-- CONTENT -->
    <section class="skills-box">
      <h1 class="animate left delay-1">
        My <span style="color: #38bdf8; font-weight: bold">Skills</span>
      </h1>
      <p class="animate left delay-2">
        Here are some of the technologies and skills I work with regularly, along with my
        proficiency level.
      </p>

      <div class="skill" v-for="(skill, index) in skills" :key="skill.name">
        <div class="skill-header animate left" :style="{ animationDelay: `${0.3 + index * 0.2}s` }">
          <span>{{ skill.name }}</span>
          <span>{{ skill.level }}%</span>
        </div>
        <div class="skill-bar animate bottom" :style="{ animationDelay: `${0.4 + index * 0.2}s` }">
          <div class="fill" :style="{ width: skill.level + '%' }"></div>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup>
import { ref } from 'vue'

const skills = ref([
  { name: 'HTML/CSS', level: 95 },
  { name: 'JavaScript', level: 90 },
  { name: 'Vue.js', level: 85 },
  { name: 'MySQL', level: 75 },
  { name: 'Git', level: 90 },
  { name: 'REST APIs', level: 85 },
])
</script>

<style scoped>
.skills {
  position: relative;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  padding: 100px 20px;
  color: #e5e7eb;
  overflow: hidden;
}

.bg-video {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -2;
  filter: blur(12px);
}

.overlay {
  position: absolute;
  inset: 0;
  background: rgba(2, 6, 23, 0.75);
  z-index: -1;
}

.skills-box {
  max-width: 800px;
  width: 100%;
  text-align: center;
  z-index: 1;
  margin-top: 90px;
}

.skills-box h1 {
  font-size: 42px;
  margin-bottom: 12px;
  color: white;
}

.skills-box h1 span {
  color: #38bdf8;
  font-weight: 800;
}

.skills-box p {
  font-size: 18px;
  color: #cbd5f5;
  margin-bottom: 30px;
}

.skill {
  margin-bottom: 24px;
}

.skill-header {
  display: flex;
  justify-content: space-between;
  font-weight: 600;
  margin-bottom: 6px;
}

.skill-bar {
  width: 100%;
  height: 16px;
  background: rgba(70, 86, 126, 0.6);
  border-radius: 12px;
  overflow: hidden;
}

.skill-bar .fill {
  height: 100%;
  background-color: #38bdf8;
  width: 0;
  border-radius: 12px;
  transition: width 1.2s ease;
}

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

@keyframes fadeIn {
  to {
    opacity: 1;
    transform: translate(0, 0);
  }
}

@media (min-width: 768px) {
  .skills-box {
    text-align: left;

    opacity: 1;
    transform: translate(0, 0);
  }
}

@media (min-width: 768px) {
  .skills-box {
    text-align: left;
  }
}

@media (max-width: 768px) {
  .skills {
    overflow: auto;
    min-height: auto;
    padding-top: 80px;
  }
}
</style>
