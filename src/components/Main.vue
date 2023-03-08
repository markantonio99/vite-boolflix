<template>
    <div class="content-movie">
      <ul class="items_flex">
        <li class="items_movie" v-for="movie in movies" :key="movie.id">
          <h2>{{ movie.title }}</h2>
          <p>Original Title: {{ movie.original_title }}</p>
          <p>Language: {{ movie.original_language }}</p>
          <p>Vote: {{ movie.vote_average }}</p>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      movies: {
        type: Array,
        required: true,
      },
    },
  };
  </script>
  
  
  
  
  
  
  
  
  
  <style lang="scss" scoped>
  
   .items_flex{
    padding: 40px 0;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
  
    background-color: blue;
    margin-top: -10px;

    .items_movie{
        flex-basis: 30%;
        padding: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
        background-color: red;
        color: white;
        border: 4px solid black;
    }



   }
   
 
  
  
  
  
   
  </style>