<template>
  <div class="movie">
    <p>{{movie.Title}}</p>
    <p class="year">{{movie.Year}}</p>
    <img :src="movie.Poster" width="250px" height="333px" />
    <br />
  </div>
</template>

<script>
export default {
  name: "Movie",
  props: ["movie"],
  methods: {
    log() {
      console.log(this.movie);
    }
  }
};
</script>

<style scoped>
img {
  margin-top: 1rem;
}
.year {
  margin-top: 0.5rem;
}
.movie {
  background-color: lightgray;
  padding: 1rem;
  margin: 1rem;
  border: 2px black solid;
  border-radius: 5px;
  width: 250px;
  height: 420px;
}
</style>