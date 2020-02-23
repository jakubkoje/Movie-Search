<template>
  <div id="app">
    <Header />
    <Search @send-movies="onSearch" />
    <Movies :movies="movies" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Movies from "./components/Movies";
import Search from "./components/Search";
export default {
  name: "app",
  components: {
    Header,
    Movies,
    Search
  },
  data: function() {
    return {
      movies: []
    };
  },
  methods: {
    onSearch(movies) {
      this.movies = movies;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
* {
  padding: 0;
  margin: 0;
}
</style>
