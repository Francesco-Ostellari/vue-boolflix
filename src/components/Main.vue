<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col">
          <h1>FILM</h1>
          <div v-if="inputSearch.movies.length > 0" class="card-container p-5">
            <Card v-for="(movie, index) in inputSearch.movies" :key="index+'movies'"
              :title="movie.title" 
              :original="movie.original_title" 
              :lang="movie.original_language"
              :vote="movie.vote_average"
              :image="`https://image.tmdb.org/t/p/w342${movie.poster_path}`">
            </Card>
          </div>
          <h2 v-else>Nessun film trovato</h2>
          <h1>SERIE TV</h1>
          <div class="card-container p-5" v-if="inputSearch.series.length > 0">
            <Card v-for="(serie, index) in inputSearch.series" :key="index+'tv'"
              :title="serie.name" 
              :original="serie.original_name" 
              :lang="serie.original_language"
              :vote="serie.vote_average"
              :image="`https://image.tmdb.org/t/p/w342${serie.poster_path}`">
            </Card>
          </div>
          <h2 v-else>Nessuna Serie TV trovata</h2>
        </div>
      </div>
    </div>
  </main>
</template>

<script>

import Card from './Card.vue'

export default {
  name: "Main",
  props: ["inputSearch"], 
  data() {
    return {

    }
      
  },
  components: {
		Card,
	}
}
</script>

<style lang="scss">
  main {
    background-color: #211F1F;
    .card-container {
      display: flex;
      flex-wrap: wrap;
    }
    h1, h2 {
      color: white;
    }
  }
</style>