<template>
  <header class="header">
    <nav class="nav">
      <RouterLink to="/" class="logo">Aleksandar Jovanovic</RouterLink>

      <!-- HAMBURGER -->
      <button class="hamburger" @click="mobileOpen = !mobileOpen">☰</button>

      <!-- DESKTOP LINKS -->
      <div class="links desktop">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/skills">Skills</RouterLink>
        <RouterLink to="/projects">Projects</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
      </div>
    </nav>
  </header>

  <!-- MOBILE MENU -->
  <div class="mobile-menu" v-if="mobileOpen">
    <RouterLink to="/" @click="closeMobile">Home</RouterLink>
    <RouterLink to="/about" @click="closeMobile">About</RouterLink>
    <RouterLink to="/skills" @click="closeMobile">Skills</RouterLink>
    <RouterLink to="/projects" @click="closeMobile">Projects</RouterLink>
    <RouterLink to="/contact" @click="closeMobile">Contact</RouterLink>
  </div>

  <main class="page">
    <RouterView />
  </main>
</template>

<script setup>
import { ref } from 'vue'

const mobileOpen = ref(false)

function closeMobile() {
  mobileOpen.value = false
}
</script>

<style scoped>
.header {
  background-color: rgba(2, 6, 23, 0.95); /* skoro crna, ne meša se sa videom */
  color: #e5e7eb;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 70px;
  z-index: 1000;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0, 0.25);
}

.nav {
  max-width: 1100px;
  height: 100%;
  margin: 0 auto;

  display: flex;
  align-items: center;
  justify-content: space-around;
  padding: 0 25px;
}

/* LOGO */
.logo {
  font-size: 22px;
  font-weight: 700;
  color: #38bdf8;
  text-decoration: none;
}

/* LINKS */
.links {
  display: flex;
  gap: 28px;
}

.links a {
  color: #e5e7eb;
  text-decoration: none;
  font-size: 16px;
  font-weight: 500;
  transition: all 0.25s ease;
}

/* hover */
.links a:hover {
  color: #38bdf8;
}

/* aktivna ruta */
.links a.router-link-active {
  color: #38bdf8;
  border-bottom: 2px solid #38bdf8;
  padding-bottom: 4px;
}

.content {
  padding-top: 70px;
}

.hamburger {
  display: none;
  font-size: 32px;
  background: none;
  border: none;
  cursor: pointer;
  color: #38bdf8; /* izražajna plava */
}

.links.desktop {
  display: flex;
  gap: 28px;
}

/* sakrij desktop na mobilnom */
@media (max-width: 768px) {
  .links.desktop {
    display: none;
  }

  .hamburger {
    display: block;
  }
}

.mobile-menu {
  position: fixed;
  top: 70px;
  right: 1px;
  width: 220px;
  background-color: rgba(2, 6, 23, 0.95);
  border-radius: 16px;
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.18);
  padding: 18px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  z-index: 999;
  animation: menuSlide 0.25s ease;
}

.mobile-menu a {
  text-decoration: none;
  color: #38bdf8;
  font-weight: 500;
  padding: 10px 12px;
  border-radius: 8px;
  transition: 0.2s;
}

@keyframes menuSlide {
  from {
    opacity: 0;
    transform: translateY(-10px) scale(0.98);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.header {
  position: sticky;
  top: 0;
  background-color: rgba(2, 6, 23, 0.95); /* skoro crna, ne meša se sa videom */
  backdrop-filter: blur(10px);
  z-index: 1000;
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 40px;
}
</style>
