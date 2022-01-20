<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col">
          <ul class="ul-movies">
            <li class="li-movies" v-for="(movie, index) in inputSearch " :key="index">
              <div>
                TITOLO: {{movie.title}}
              </div>
              <div>
                TITOLO ORIGINALE: {{movie.original_title}}
              </div>
              <div>
                LINGUA: {{movie.original_language}}
              </div>
              <div>
                VOTO: {{movie.vote_average}}
              </div>
              <hr>
            </li>
          </ul>
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
      
  },
  methods: {
    
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