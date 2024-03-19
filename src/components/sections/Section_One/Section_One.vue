<!-- I det her component har jeg brugt v-for, hvilket egentlig bare er en forEach eller map, jeg har også brugt v-bind (:) som lader mig "binde" HTML atributter (eller classes) til variabler,
 f.eks. book.title i mit array. -->

<template>
  <div class="gridLayout_5">
    <div v-for="book in books" :key="book.title">
      <figure>
        <img :src="book.img" :alt="book.title" />
        <figcaption>
          <h3>{{ book.title }}</h3>
          <p>{{ book.author }} | {{ book.releaseDate }}</p>
        </figcaption>
      </figure>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const books = ref([
  {
    title: 'The Great Gatsby',
    author: 'F. Scott Fitzgerald',
    releaseDate: '1925',
    img: '/images/Section_One/the_great_gatsby.jpg'
  },
  {
    title: 'To Kill a Mockingbird',
    author: 'Harper Lee',
    releaseDate: '1960',
    img: '/images/Section_One/to_kill_a_mockingbird.jpg'
  },
  {
    title: '1984',
    author: 'George Orwell',
    releaseDate: '1949',
    img: '/images/Section_One/1984.jpg'
  },
  {
    title: 'The Catcher in the Rye',
    author: 'J.D. Salinger',
    releaseDate: '1951',
    img: '/images/Section_One/the_catcher_in_the_rye.jpg'
  },
  {
    title: 'Pride and Prejudice',
    author: 'Jane Austen',
    releaseDate: '1813',
    img: '/images/Section_One/pride_and_prejudice.jpg'
  },
  {
    title: 'The Hobbit',
    author: 'J.R.R. Tolkien',
    releaseDate: '1937',
    img: '/images/Section_One/the_hobbit.jpg'
  },
  {
    title: 'The Da Vinci Code',
    author: 'Dan Brown',
    releaseDate: '2003',
    img: '/images/Section_One/the_da_vinci_code.jpg'
  },
  {
    title: 'The Outsiders',
    author: 'S.E. Hinton',
    releaseDate: '1967',
    img: '/images/Section_One/the_outsiders.jpg'
  },
  {
    title: 'The Hunger Games',
    author: 'Suzanne Collins',
    releaseDate: '2008',
    img: '/images/Section_One/the_hunger_games.jpg'
  },
  {
    title: 'The Alchemist',
    author: 'Paulo Coelho',
    releaseDate: '1988',
    img: '/images/Section_One/the_alchemist.jpg'
  }
])
</script>

<style scoped>
.gridLayout_5 figcaption {
  margin-block: 0.8rem;
  text-align: center;
}

.gridLayout_5 figcaption p {
  font-style: italic;
}

.gridLayout_5 figure {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 2px solid #f2f2f2;
  border-radius: 10px;
  padding: 0.5rem;
  transform: scale(0.99);
  transition:
    transform 0.4s,
    border 0.4s;
}

.gridLayout_5 figure:hover {
  transform: scale(1.1);
  border: 2px solid green;
}

.gridLayout_5 figure img {
  width: 150px;
  height: 200px;
  overflow: hidden;
}
</style>
