<template>
  <div class="container">
    <div v-if="loading" class="loader"/>
    <div v-else class="jokes">
      <Joke
        v-for="joke in jokes"
        :key="joke.id"
        :id="joke.id"
        :joke="joke.joke"
      />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Joke from '../components/Joke'

export default {
  components: {
    Joke,
  },
  data() {
    return {
      jokes: [],
      loading: false,
    }
  },
  async fetch() {
    try {
      const config = {
        headers: {
          Accept: 'application/json',
        },
      }
      this.loading = true
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      this.jokes = res.data.results
      setTimeout(() => (this.loading = false), 1000)
      console.log(this.jokes)
    } catch (err) {
      console.log(err)
    }
  },
  head() {
    return {
      title: 'Dad Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Get your jokes here',
        },
      ],
    }
  },
}
</script>

<style>
.jokes {
  width: 100%;
  height: 100%;
  overflow-y: scroll;
  padding-right: 17px; /* Increase/decrease this value for cross-browser compatibility */
  box-sizing: content-box; /* So the width will be 100% + 17px */
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* Internet Explorer 10+ */
}
</style>
