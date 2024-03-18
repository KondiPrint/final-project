<script setup>
import NavBar from './components/NavBar.vue'
import MainContent from './components/MainContent.vue'
</script>

<template>
  <header>
    <NavBar />
  </header>

  <main>
    <MainContent />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
</style>
