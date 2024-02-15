<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div>
    <div class="nav-links">
      <RouterLink to="/" class="nav-link" active-class="active">Home</RouterLink>
      <RouterLink to="/about" class="nav-link" active-class="active">About</RouterLink>
    </div>
    <RouterView />
  </div>
</template>

<style scoped>
.nav-links {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 10px;
}

.nav-link {
  text-decoration: none;
  color: #333;
  font-size: 1.2rem;
  margin: 0 15px;
  padding: 10px;
  transition: color 0.3s ease-in-out;
}

.nav-link:hover {
  color: #007bff;
}

.active {
  color: green;
  font-weight: bold;
}
</style>
