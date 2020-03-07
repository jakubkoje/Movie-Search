<template>
  <div class="search">
    <p>Try to search some movie.</p>
    <input
      type="text"
      name="search"
      id="search"
      placeholder="Movie name"
      v-model="input"
    />
    <button @click="getMovies">Search</button>
  </div>
</template>

<script>
import Axios from 'axios';
export default {
  name: 'Search',
  data: function() {
    return {
      movies: [],
      input: '',
    };
  },
  methods: {
    sendMovies() {
      //eslint ignore no-console
      console.log(this.movies);
      this.$emit('sendMovies', this.movies);
    },
    getMovies() {
      Axios.get(`https://www.omdbapi.com/?apikey=382ff7cf&s=${this.input}`)
        .then((res) => {
          this.movies = res.data.Search;
        })
        .then(() => this.$emit('send-movies', this.movies))
        .catch((err) => console.log(err));
    },
  },
};
</script>

<style scoped>
.search {
  margin: 2rem 0 1rem 0;
}

p {
  margin-bottom: 1rem;
}

button {
  margin-left: 1rem;
}
</style>
