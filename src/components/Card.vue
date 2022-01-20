<template>
  <div class="card">
    <div class="layout-card">
      <img :src="image" :alt="title">
        <span>TITOLO: {{title}}</span>
        <span>TITOLO ORIGINALE: {{original}}</span>
        <span>LINGUA: <i :class="'flag flag-' + getFlags(lang)"></i></span>
        <span class="voto">VOTO: {{vote}}</span>
    </div>  
  </div>
</template>

<script>
export default {
  name: "Card",
  props: [
    'title',
    'image',
    'original',
    'lang',
    'vote',
  ],
  methods: {
    getFlags(lang){
      switch (lang){
        case 'en':
          return 'us';
        case 'ko':
          return 'kr';
        case 'ja':
          return 'jp';
        case 'ur':
          return 'pk';
        case 'zh':
          return 'cn';
        case 'el':
          return 'gr';
        default:
          return lang;
      }
    }
  }
}
</script>

<style lang="scss">
.card {
  padding: 0.5em 1em;
  width: 400px;
  height: 630px;
  .layout-card {
    padding: 1em 1.5em;
    height: 100%;
    border: 1px solid black;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 1.2em;
    img {
      height: 100%;
      width: 100%;
    }
    span {
      text-align: center;
    }
  }
}
</style>