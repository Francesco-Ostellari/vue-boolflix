<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="col">
          <ul>
            <li>
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
  props: ["valueHeader"],
  data() {
    return {
      movies: [],
      }
      
  },
  methods: {
    getMovies() {
      axios.get()
      .then()
      .catch()
    }
  }
}
</script>

<style>

</style>