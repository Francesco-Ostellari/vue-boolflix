<template>
  <div id="app">
    <Header @doSearch="getSelect($event)" :inputValue="valueHeader"/>
    <Main :valueHeader="valueHeader"/>
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
      valueHeader: '',
      staticApi: "https://api.themoviedb.org/3/search/movie?api_key=295649702f864d86aa6f022b7f8435fd&query="
    };
  },
  methods: {
    getSelect(value) {
      this.valueHeader = this.staticApi + value;
    }
  },
};
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap';
</style>