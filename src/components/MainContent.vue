<template>
  <div class="wrapper">
    <div class="main__title">
      <h1>My first Vue page</h1>
      <h2>Here you can see some of the features that Vue allows</h2>
    </div>

    <div class="sections" id="section_one">
      <h3>Here is a section to show a list of books, i've heard, is worth reading</h3>
      <button @click="openSectionOne = !openSectionOne" class="btn">Close Section One</button>
      <Section_One v-show="openSectionOne" />
    </div>

    <div class="sections" id="section_two">
      <h3>Here is a section to show a list of books, i've heard, is worth reading</h3>
      <button @click="openSectionTwo = !openSectionTwo" class="btn">Close Section Two</button>
      <Section_Two v-show="openSectionTwo" />
    </div>

    <div class="sections" id="section_three">
      <h3>Here is a section to show a list of books, i've heard, is worth reading</h3>
      <button @click="openSectionThree = !openSectionThree" class="btn">Close Section Three</button>
      <Section_Three v-show="openSectionThree" />
    </div>
  </div>
</template>

<script setup>
import Section_One from './sections/Section_One/Section_One.vue'
import Section_Two from './sections/Section_Two/Section_Two.vue'
import Section_Three from './sections/Section_Three/Section_Three.vue'
import { ref } from 'vue'

let openSectionOne = ref(true)
let openSectionTwo = ref(true)
let openSectionThree = ref(true)

// Jeg fandt ud af jeg ikke behøvede at lave funktioner, men istedet skrive dem in i @click ved knappen. Ved simple ting.

/* const toggleSectionOne = () => {
  openSectionOne.value = !openSectionOne.value
}
const toggleSectionTwo = () => {
  openSectionTwo.value = !openSectionTwo.value
}
const toggleSectionThree = () => {
  openSectionThree.value = !openSectionThree.value
} */
</script>

<style scoped>
.main__title {
  text-align: center;
  margin-block: 4rem 6rem;
}

h1 {
  font-size: 4rem;
}

.sections {
  text-align: center;
  margin-bottom: 5rem;
}

.sections button,
h3 {
  margin-bottom: 2rem;
}
</style>
./sections/Section_Two/Section_Two.vue ./sections/Section_one/Section_One.vue
