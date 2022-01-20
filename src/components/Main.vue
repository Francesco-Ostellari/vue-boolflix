<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col">
          <h1>FILM</h1>
          <ul v-if="inputSearch.movies.length > 0" class="ul-movies">
            <li class="li-movies" v-for="(movie, index) in inputSearch.movies" :key="index+'movies'">
              <div>
                TITOLO: {{movie.title}} 
              </div>
              <div>
                TITOLO ORIGINALE: {{movie.original_title}} 
              </div>
              <div>
                LINGUA: <i :class="(movie.original_language == 'en') ? 'flag flag-us' : `flag flag-${ movie.original_language }`"></i>
              </div>
              <div>
                VOTO: {{movie.vote_average}} 
              </div>
              <hr>
            </li>
          </ul>
          <h2 v-else>Nessun film trovato</h2>
          <h1>SERIE TV</h1>
          <ul class="ul-movies" v-if="inputSearch.series.length > 0">
            <li class="li-movies" v-for="(serie, index) in inputSearch.series" :key="index+'series'">
              <div>TITOLO: {{serie.name}}</div>
              <div>TITOLO ORIGINALE: {{serie.original_name}}</div>
              <div>LINGUA: <i :class="(serie.original_language == 'en') ? 'flag flag-us' : `flag flag-${serie.original_language}`"></i></div>
              <div>VOTO: {{serie.vote_average}}</div>
              <hr>
            </li>
          </ul>
          <h2 v-else>Nessuna Serie TV trovata</h2>
        </div>
      </div>
    </div>
  </main>
</template>

<script>

export default {
  name: "Main",
  props: ["inputSearch"], 
  data() {
    return {

    }
      
  }
}
</script>

<style lang="scss">
.ul-movies {
  list-style-type: disc;
  .li-movies {
    display: block;
  }
}

</style>