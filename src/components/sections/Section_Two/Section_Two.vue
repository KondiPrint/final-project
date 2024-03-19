<!-- I den her component har jeg brugt 'ref' til at binde quote og author til content og author i det API jeg kalder ind.
Det vil sige at quote/author automatisk opdatere UI'et når der kommer ny data -->

<template>
  <section>
    <div>
      <h2>{{ quote }}</h2>
      <p>{{ author }}</p>
    </div>
    <button @click="getQuote" class="btn">New quote</button>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const quote = ref('')
const author = ref('')

const getQuote = async () => {
  try {
    const response = await fetch('https://api.quotable.io/random')
    const data = await response.json()
    quote.value = data.content
    author.value = data.author
  } catch (error) {
    console.error('An error occured trying to get a quote', error)
  }
}

getQuote()
</script>

<style scoped>
p {
  font-style: italic;
  font-size: 1.5rem;
}

h2 {
  font-size: 2rem;
}

div {
  border: 2px solid whitesmoke;
  padding: 2rem;
  border-radius: 10px;
}
</style>
