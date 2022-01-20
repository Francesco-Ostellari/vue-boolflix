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
      <input id="search" v-model="inputText" type="text" name="search" @keyup.enter="getMerged">
      <button class="btn btn-primary" type="submit" @click="getMerged"> Cerca </button>
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
      merged: {
				movies: [],
				series: [],
			},
      query: 'https://api.themoviedb.org/3/search/',
			api_key: '53982486ea69d909f7fc01dea5daec6b',
    }
  },
  methods: {
    getMovies: function () {
      const movie = 'movie';
      const parameters = {
				api_key: this.api_key,
				query: this.inputText,
			};
      axios.get(`${this.query}${movie}`, { params: parameters })
			.then((result) => {
				this.merged.movies = result.data.results;
			})
			.catch((error) => {
				console.log(error);
			})
    },
    getSeries: function () {
      const tv = 'tv';
			const parameters = {
				api_key: this.api_key,
				query: this.inputText,
			};
			axios.get(`${this.query}${tv}`, { params: parameters })
				.then((result) => {
					this.merged.series = result.data.results;
					
				})
				.catch((error) => {
					console.log(error);
				});
    },

    getMerged: function () {
      this.getMovies();
			this.getSeries();
			setTimeout(() => {
				this.$emit('sendSelect', this.merged);
			}, 700);
    },
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