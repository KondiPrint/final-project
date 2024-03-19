<template>
  <nav class="pageheader__nav">
    <img alt="Vue logo" src="../assets/logo.svg" width="42" height="42" />
    <menu class="nav__menu">
      <li><a href="#section_one">Book-list</a></li>
      <li><a href="#section_two">Random Quote</a></li>
      <li><a href="#section_three">Todo-list</a></li>
    </menu>
  </nav>
</template>

<script setup></script>

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
  gap: 1rem;
  list-style-type: none;
  margin: 0 auto;
}

.nav__menu li a {
  text-decoration: none;
  padding: 0.5rem;
  color: #f0f0f0;
  transition:
    background-color 0.5s,
    border-radius 0.5s,
    color 0.5s;
}

.nav__menu li a:hover {
  background-color: #7fffd4;
  border-radius: 10px;
  color: #222222;
}
</style>
