<template>
    <div class="container-head">
          <div class="items_head_logo">
               <figure class="logo_head">
                   <img src="../assets/Netflix-logo.png" alt="">
               </figure>
          </div>
          <div class="items_head_search">
                  <label class="search-title">Search Movie:</label>
                  <input class="search-input" v-model="search" @keyup.enter="fetchMovies" placeholder="Srivi il titolo qui..." />
                  <button class="button_search" @click="fetchMovies">Cerca film</button>
                  <div v-if="card" class="card">{{ card }}</div>
          </div>
          
      
    </div>

  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        search: '',
        card: '',
      };
    },
    methods: {
      fetchMovies() {
        axios
          .get(
            `https://api.themoviedb.org/3/search/movie?api_key=17ff2cbf49b15d4d84e7f4fe34a42391&query=${this.search}`
          )
          .then((response) => {
            this.$emit('movies-fetched', response.data.results);
          })
          .catch((card) => {
            this.card = card.response.data.status_message;
          });
      },
    },
  };
  </script>
  

<style lang="scss" scoped>
   .container-head{
    display: flex;
    justify-content: center;
    padding: 20px 50px;
    background-color: black;
    color: white;
    align-items: center;

       .imput_search{
        border: 1px solid blue;
       }

       .items_head_logo{
        width: 50%;
       }


       .items_head_search{
        flex-grow: 1;
        display: flex;
        justify-content: end;
        align-items: center;
      
       }


     .logo_head{
        max-width: 15%;
     }

     .search-input{
        margin: 0 10px;
     }

     .button_search{
       padding: 1px 20px;
     }


   }
</style>