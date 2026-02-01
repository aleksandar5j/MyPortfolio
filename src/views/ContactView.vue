<template>
  <main class="contact">
    <!-- VIDEO BACKGROUND -->
    <video autoplay muted loop playsinline class="bg-video">
      <source src="/src/videos-images/contact.mp4" type="video/mp4" />
    </video>

    <!-- OVERLAY -->
    <div class="overlay"></div>

    <!-- CONTENT -->
    <section class="contact-box">
      <h1 class="animate left delay-1"><span>Let's</span> Connect</h1>

      <p class="animate left delay-2">Find me on these platforms or get in touch directly.</p>

      <div class="links">
        <a
          href="https://github.com/aleksandar5j"
          target="_blank"
          class="card animate bottom delay-3"
        >
          <img src="/src/assets/icons/github.svg" alt="GitHub" />
          <span>GitHub</span>
        </a>

        <a
          href="https://www.linkedin.com/in/aleksandar-jovanović-622879339/"
          target="_blank"
          class="card animate bottom delay-4"
        >
          <img src="/src/assets/icons/linkedin.svg" alt="LinkedIn" />
          <span>LinkedIn</span>
        </a>

        <a
          class="card animate bottom delay-5"
          target="_blank"
          rel="noopener noreferrer"
          @click="openEmailPopup()"
        >
          <img src="/src/assets/icons/email.svg" alt="Email" />
          <span>Email</span>
        </a>

        <a href="/MojCV.pdf" download="aleksandar'sCV.pdf" class="card animate bottom delay-6">
          <img src="/src/assets/icons/cv.svg" alt="CV" />
          <span>Download CV</span>
        </a>
      </div>
    </section>

    <div v-if="isEmailOpen" class="email-popup-overlay" @click.self="closeEmailPopup">
      <div class="email-popup animate-fade">
        <button class="close-btn" @click="closeEmailPopup">×</button>
        <h2>Contact Me</h2>
        <p>You can reach me at:</p>
        <input type="text" readonly :value="myEmail" @click="$event.target.select()" />
        <p class="info">Click the input to copy the email</p>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'

const isEmailOpen = ref(false)
const myEmail = 'acaajovanovic5@gmail.com'

function openEmailPopup() {
  isEmailOpen.value = true
}

function closeEmailPopup() {
  isEmailOpen.value = false
}
</script>

<style scoped>
.contact {
  min-height: 100vh;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #e5e7eb;
  padding: 40px 20px;
  overflow: hidden;
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

/* OVERLAY da tekst bude čitljiv */
.overlay {
  position: fixed;
  inset: 0;
  background: rgba(2, 6, 23, 0.75);
  z-index: -1;
}

/* CONTENT BOX */
.contact-box {
  max-width: 900px;
  width: 100%;
  text-align: center;
  margin-top: 50px;
  z-index: 1;
}

.contact-box h1 {
  font-size: 48px;
  font-weight: 800;
  margin-bottom: 12px;
  color: #38bdf8;
}

.contact-box h1 span {
  color: white;
}

.contact-box p {
  font-size: 18px;
  color: #cbd5f5;
  margin-bottom: 50px;
}

/* GRID */
.links {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 24px;
}

/* CARD */
.card {
  background: rgba(15, 23, 42, 0.85);
  border: 1px solid rgba(56, 189, 248, 0.25);
  border-radius: 20px;
  padding: 30px 20px;

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 14px;
  cursor: pointer;

  text-decoration: none;
  color: #e5e7eb;
  font-weight: 600;
  transition: all 0.3s ease;
}

.card img {
  width: 48px;
  height: 48px;
  filter: invert(1);
}

.card:hover {
  transform: translateY(-6px);
  border-color: #38bdf8;
  background: rgba(15, 23, 42, 0.95);
}

.card:hover img {
  filter: invert(61%) sepia(91%) saturate(476%) hue-rotate(176deg);
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
.delay-6 {
  animation-delay: 1.2s;
}

@keyframes fadeIn {
  to {
    opacity: 1;
    transform: translate(0, 0);
  }
}

.email-popup-overlay {
  position: fixed;
  inset: 0;
  background: rgba(2, 6, 23, 0.85);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 10000;
}

.email-popup {
  background: #0f172a;
  padding: 40px;
  border-radius: 20px;
  text-align: center;
  color: #e5e7eb;
  max-width: 400px;
  width: 90%;
  position: relative;
}

.email-popup h2 {
  margin-bottom: 12px;
  color: #38bdf8;
}

.email-popup input {
  width: 100%;
  padding: 12px 16px;
  border-radius: 12px;
  border: 1px solid #38bdf8;
  background: #1e293b;
  color: #e5e7eb;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
  margin: 10px;
}

.email-popup .info {
  font-size: 14px;
  color: #94a3b8;
  margin-top: 8px;
}

.close-btn {
  position: absolute;
  top: 12px;
  right: 16px;
  font-size: 24px;
  background: none;
  border: none;
  color: #e5e7eb;
  cursor: pointer;
}

/* ANIMATION */
.animate-fade {
  opacity: 0;
  animation: fadeInPopup 0.3s forwards;
}

@keyframes fadeInPopup {
  to {
    opacity: 1;
  }
}
</style>
