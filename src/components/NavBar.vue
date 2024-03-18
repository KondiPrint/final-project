<script setup></script>

<template>
  <nav class="pageheader__nav">
    <img alt="Vue logo" class="logo" src="../assets/logo.svg" width="42" height="42" />
    <menu class="nav__menu">
      <li><a href="#section_one">Section_one</a></li>
      <li><a href="#section_two">Section_two</a></li>
      <li><a href="#section_three">Section_three</a></li>
    </menu>
  </nav>
</template>

<style scoped>
.pageheader__nav {
  padding: 0.5rem 1rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
  align-items: center;
  width: 100%;
}
.nav__menu {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
  list-style-type: none;
  margin: 0 auto;
  color: rgba(235, 235, 235, 0.64);
  justify-content: space-evenly;
  width: 100%;
}

.nav__menu li a {
  text-decoration: none;
  text-transform: none;
  color: rgba(60, 60, 60, 0.66);
}

@media (min-width: 640px) {
  .pageheader__nav {
    flex-wrap: nowrap;
  }

  .nav__menu {
    flex-wrap: nowrap;
  }
}
</style>
