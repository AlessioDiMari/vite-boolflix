<script>
import axios from 'axios';
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';
import { store } from './store.js';

export default{
  data(){
    return{
      store,
    }
  },

  created(){

    axios.get('https://api.themoviedb.org/3/movie/now_playing?api_key=70b1b8819a29487e3d43e24ef439ddeb')
    .then(res => {
      console.log(res.data.results)
      this.store.movies = res.data.results
    })

  },

  components : {
    AppHeader,
    AppMain,
  },

  methods: {
    
    searchMovie() {

      axios.get('https://api.themoviedb.org/3/search/movie?api_key=70b1b8819a29487e3d43e24ef439ddeb&language=it-IT&query=' + this.store.searchText)
      .then(res => {
        console.log(res.data.results)
        this.store.movies = res.data.results
      });
    }
  }

}
</script>

<template>

  <AppHeader @search="searchMovie()"></AppHeader>
  <AppMain></AppMain>

</template>

<style>

</style>
