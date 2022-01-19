<template>
  <div>
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
      <input id="search" type="text" v-model="inputText" name="search">
      <button @click="$emit('doSearch', inputText)"
      class="btn btn-primary"
      type="submit"
      >
      Cerca
    </button>
    </div>
  </div>
</template>

<script>

export default {
  name: "Header",
  props: {
    inputValue: {
      type: String,
    }
  },
  data () {
    return {
      inputText: '',
    }
  },
}
</script>

<style lang="scss">
  div {
    background-color: #211F1F;
    height: 30px;
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