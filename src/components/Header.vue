<template>
  <header>
    <div class="logo"></div>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">Serie TV</a></li>
      <li><a href="#">Film</a></li>
      <li><a href="#">Originale</a></li>
      <li><a href="#">Aggiunti di recente</a></li>
      <li><a href="#">La mia lista</a></li>
    </ul>
    <div class="search-bar">
      <input @keyup.enter="getAxios" v-model="inputText" id="search" type="text"  name="search">
      <button @click="$emit('doSearch', inputText)"
      class="btn btn-primary"
      type="submit"
      >
      Cerca
      </button>
    </div>
  </header>
</template>

<script>
import axios from 'axios';
export default {
  name: "Header",
  data () {
    return {
      inputText: '',
      getMovies: [],
    }
  },
  methods: {
    getAxios: function () {
      axios.get("https://api.themoviedb.org/3/search/movie?api_key=53982486ea69d909f7fc01dea5daec6b",
      {
        params: {
          query: this.inputText
        }
      })
      .then(result => {
          this.getMovies = result.data.results
          this.$emit("sendSelect", this.getMovies)
        
      })
      .catch(error => {
          console.error(error);               
      })
    }
  },
}
</script>

<style lang="scss">
  header {
    background-color: #211F1F;
    height: 80px;
    padding-bottom: 80px;
    width: 100%;
  }.logo {
    width: 200px;
  }ul {
    list-style: none;
    li {
      display: inline-block;
      a {
        text-decoration: none;
      }
    }
  }
</style>