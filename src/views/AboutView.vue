<template>
  <main class="about">
    <!-- VIDEO BACKGROUND -->
    <video autoplay muted loop playsinline class="bg-video">
      <source src="/src/videos-images/coding.mp4" type="video/mp4" />
    </video>

    <!-- DARK OVERLAY -->
    <div class="overlay"></div>

    <!-- CONTENT -->
    <section class="about-box animate bottom delay-1">
      <!-- AVATAR -->
      <div class="avatar">
        <img src="/src/videos-images/profile1.jpg" alt="Aleksandar" />
      </div>

      <!-- TEXT -->
      <div class="text">
        <h1>About <span>Me</span></h1>

        <p>
          Hi, I'm <span>Aleksandar</span>, a passionate FullStack Web Developer. Ever since I
          discovered coding, I have loved building websites and web applications that are both
          functional and visually appealing.
        </p>

        <p>
          I'm a team player who enjoys collaborating with others, sharing ideas, and learning from
          different perspectives. I believe that the best results come from combining creativity,
          clean code, and teamwork.
        </p>

        <p>
          In my free time, I like to explore new technologies, improve my skills, and experiment
          with creative web projects. I’m always motivated to learn, grow, and take on exciting
          challenges in the world of web development.
        </p>
      </div>
    </section>
  </main>
</template>

<script setup></script>

<style scoped>
.about {
  position: relative;
  min-height: 92.2vh;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #e5e7eb;
  padding: 40px 20px;
  flex-direction: column;
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
  overflow: hidden; /* opcionalno */
}

/* OVERLAY */
.overlay {
  position: absolute;
  inset: 0;
  background: rgba(2, 6, 23, 0.75);
  z-index: -1;
}

/* ABOUT BOX */
.about-box {
  margin-top: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 700px;
  text-align: center;
  z-index: 1;
  gap: 30px;
}

.avatar img {
  width: 180px;
  height: 180px;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid #38bdf8;
  transform: translateY(-20px);
}

.text h1 {
  font-size: 42px;
  margin-bottom: 16px;
  color: white;
}

.text h1 span {
  color: #38bdf8;
  font-weight: 800;
}

.text p {
  font-size: 18px;
  line-height: 1.8;
  color: #cbd5f5;
  margin-bottom: 20px;
}

/* ANIMATIONS */
.animate {
  opacity: 0;
  animation: fadeIn 0.8s ease forwards;
}

.bottom {
  transform: translateY(40px);
}

.delay-1 {
  animation-delay: 0.3s;
}

@keyframes fadeIn {
  to {
    opacity: 1;
    transform: translate(0, 0);
  }
}

/* RESPONSIVE */
@media (min-width: 768px) {
  .about-box {
    gap: 40px;
  }

  .text {
    text-align: left;
  }
}
</style>
