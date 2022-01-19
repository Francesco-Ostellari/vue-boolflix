<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="col">
          <ul>
            <li v-for="(movie, index) in valueHeader " :key="index">
              <div>
                {{movie.title}}
              </div>
              <div>
                {{movie.original_title}}
              </div>
              <div>
                {{movie.original_language}}
              </div>
              <div>
                {{movie.vote_average}}
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: "Main",
  props: {
    valueHeader: {
      type: String,
    }, 
  }, 
  data() {
    return {
      movies: null,
      }
      
  },
  mounted() {
    this.getMovies();
  },

  methods: {
    getMovies() {
      axios.get(this.valueHeader)
      .then((result) => {
        this.movies = result.data.results
      })
      .catch((error) => {
        console.log(error);
      });
    }
  }
}
</script>

<style>

</style>