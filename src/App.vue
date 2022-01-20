<template>
  <div id="app">
    <Header @sendSelect="getSelect($event)"/>
    <Main :inputSearch="boolflixApi"/>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer
  },
  data() {
    return {
      boolflixApi: {
        movies: [],
        series: [],
      },
    };
  },
  methods: {
    getSelect(value) {
      this.boolflixApi.movies = value.movies;
      this.boolflixApi.series = value.series;
    },
  },
};
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap';
  @import '~mdb-ui-kit/css/mdb.min.css'; 
</style>