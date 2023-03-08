<template>
    <div>
      <Header @movies-fetched="onMoviesFetched" />
      <Main :movies="movies" />
    </div>
  </template>
  
  <script>
  import Header from './components/Header.vue';
  import Main from './components/Main.vue';
  
  export default {
    components: {
      Header,
      Main,
    },
    data() {
      return {
        movies: [],
      };
    },
    methods: {
      onMoviesFetched(movies) {
        this.movies = movies;
      },
    },
  };
  </script>
  

<style lang="scss">
@use '../src/components/style/generalstyle.scss'
</style>
