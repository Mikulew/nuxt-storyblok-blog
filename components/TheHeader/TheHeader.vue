<template>
  <header class="main-header">
    <nav class="main-nav">
      <ul class="nav-links">
        <nuxt-link class="nav-link" tag="li" to="/">
          <a>All posts</a>
        </nuxt-link>
        <nuxt-link class="nav-link" tag="li" to="/about">
          <a>About</a>
        </nuxt-link>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
.main-header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 4.5rem;
  background: #022d30;
}

.main-nav {
  height: 100%;
}

.nav-links {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-link {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  margin: 0 1rem;
  padding: 0.3rem;
}

.nav-link.nuxt-link-exact-active {
  border-bottom: 3px solid #06c4d1;
}

.nav-link a {
  display: block;
  text-decoration: none;
  color: white;
}

.nav-link a:hover,
.nav-link a:active,
.nav-link.nuxt-link-exact-active a {
  color: #06c4d1;
}
</style>
