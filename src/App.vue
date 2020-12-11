<template>
  <div id="app">
    <Header title='Popular Tv Shows'></Header>
    <Card v-bind:tvshowlist="tvShow"></Card>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Card from './components/Card.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Card,
  },
  data(){
    return{
      tvShow: [
        //the details of the card like: name, poster path, and overivew
      ]
    };
  },
  mounted(){
    axios.get('https://api.themoviedb.org/3/tv/popular?api_key=52af9ce1b74868693e85b83ece5c946a&language=en-US&page=1')
    .then((response) => {
      this.tvShow = response.data.results;
    });
  }
};
</script>

<style>
  *{
    margin: 0px;
    padding: 0px;
  }
</style>
