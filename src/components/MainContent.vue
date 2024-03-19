<template>
  <div class="wrapper">
    <div class="main__title">
      <h1 class="fancy">My first Vue page</h1>
      <h2>Here you can see some of the features that Vue allows</h2>
    </div>

    <section class="sections" id="section_one">
      <h2 class="fancy" style="--w: 50vw; --c: #c44d58; --b: 4px; --g: 40px">Books</h2>
      <button @click="openSectionOne = !openSectionOne" class="btn">Close Section One</button>
      <Section_One v-show="openSectionOne" />
    </section>

    <section class="sections" id="section_two">
      <h2 class="fancy" style="--w: 50vw; --c: #8a9b0f; --b: 4px; --g: 40px">Quotes</h2>
      <button @click="openSectionTwo = !openSectionTwo" class="btn">Close Section Two</button>
      <Section_Two v-show="openSectionTwo" />
    </section>

    <section class="sections" id="section_three">
      <h2 class="fancy" style="--w: 50vw; --c: #b52fbf; --b: 4px; --g: 40px">Todo-list</h2>
      <button @click="openSectionThree = !openSectionThree" class="btn">Close Section Three</button>
      <Section_Three v-show="openSectionThree" />
    </section>
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
  margin-block: 6rem 6rem;
}

.sections {
  text-align: center;
  margin-bottom: 5rem;
}

.sections .btn {
  margin-bottom: 5rem;
}

h2 {
  font-size: 1.8rem;
}

h1 {
  font-size: 3rem;
}

.fancy {
  --b: 6px; /* control the border thickness */
  --w: 100px; /* control the width of the line*/
  --g: 15px; /* control the gap */
  --c: #0b486b;

  width: fit-content;
  padding: 0 1em;
  line-height: 1.6em;
  border: 1px solid;
  color: #fff;
  background:
    conic-gradient(from 45deg at left, var(--c) 25%, #0000 0) 0,
    conic-gradient(from -135deg at right, var(--c) 25%, #0000 0) 100%;
  background-size: 51% 100%;
  background-origin: border-box;
  background-repeat: no-repeat;
  border-image: linear-gradient(
      #0000 calc(50% - var(--b) / 2),
      var(--c) 0 calc(50% + var(--b) / 2),
      #0000 0
    )
    1/0 var(--w) / calc(var(--w) + var(--g));
  margin-inline: auto;
}
</style>
