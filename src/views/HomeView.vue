<script setup></script>

<template>
  <main class="home">
    <!-- VIDEO BACKGROUND -->
    <video autoplay muted loop playsinline class="bg-video">
      <source src="/src/videos-images/coding.mp4" type="video/mp4" />
    </video>

    <!-- OVERLAY -->
    <div class="overlay"></div>

    <!-- CONTENT -->
    <section class="hero">
      <h1 class="animate left delay-1"><span>Hi, I'm</span> Aleksandar</h1>

      <h2 class="animate left delay-2">FullStack Web Developer</h2>

      <p class="animate left delay-3">
        I create modern, fast and user-friendly web applications with clean code and strong UI
        focus.
      </p>

      <div class="actions animate bottom delay-4">
        <RouterLink to="/projects" class="btn primary"> View Projects </RouterLink>
        <RouterLink to="/contact" class="btn secondary"> Contact Me </RouterLink>
      </div>
    </section>
  </main>
</template>

<style scoped>
.home {
  position: relative;
  height: 100vh;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #e5e7eb;
}

/* VIDEO */
.bg-video {
  position: absolute; /* FIXED da bude preko celog ekrana */
  inset: 0;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -2;
  filter: blur(6px);
}

/* DARK OVERLAY */
.overlay {
  position: absolute;
  inset: 0;
  background: rgba(2, 6, 23, 0.75);
  z-index: -1;
}

.hero {
  text-align: center;
  max-width: 700px;
  padding: 20px;
  margin-top: 40px;
}

.hero h1 {
  font-size: 56px;
  font-weight: 800;
  color: #38bdf8;
}

.hero h1 span {
  color: white;
}

.hero h2 {
  font-size: 24px;
  color: #94a3b8;
  margin: 12px 0 20px;
}

.hero p {
  font-size: 18px;
  line-height: 1.6;
  margin-bottom: 35px;
  color: #cbd5f5;
}

/* BUTTONS */
.actions {
  display: flex;
  justify-content: center;
  gap: 20px;
}

.btn {
  padding: 14px 30px;
  border-radius: 999px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.25s ease;
}

.primary {
  background-color: #38bdf8;
  color: #020617;
}

.primary:hover {
  background-color: #0ea5e9;
  transform: translateY(-2px);
}

.secondary {
  border: 2px solid #38bdf8;
  color: #38bdf8;
}

.secondary:hover {
  background-color: #38bdf8;
  color: #020617;
  transform: translateY(-2px);
}

.animate {
  opacity: 0;
  animation: fadeIn 0.8s ease forwards;
}

/* DIRECTIONS */
.left {
  transform: translateX(-60px);
}

.bottom {
  transform: translateY(40px);
}

/* DELAYS */
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

/* KEYFRAMES */
@keyframes fadeIn {
  to {
    opacity: 1;
    transform: translate(0, 0);
  }
}
</style>
