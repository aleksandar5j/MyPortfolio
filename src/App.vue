<template>
  <header class="header">
    <nav class="nav">
      <RouterLink to="/" class="logo">Aleksandar Jovanovic</RouterLink>

      <div class="links">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/skills">Skills</RouterLink>
        <RouterLink to="/projects">Projects</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
      </div>
    </nav>

    <main>
      <RouterView></RouterView>
    </main>
  </header>
</template>

<script setup></script>

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
  justify-content: space-between;
  padding: 0 24px;
}

/* LOGO */
.logo {
  font-size: 22px;
  font-weight: 700;
  color: #38bdf8; /* izražajna plava */
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
</style>
