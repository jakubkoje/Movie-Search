<template>
  <div class="movies">
    <div v-for="movie in movies" :key="movie.imdbID">
      <Movie :movie="movie" class="movie" />
    </div>
  </div>
</template>

<script>
import Movie from "./Movie";
export default {
  name: "Movies",
  components: {
    Movie
  },
  props: ["movies"]
};
</script>

<style scoped>
.movies {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>