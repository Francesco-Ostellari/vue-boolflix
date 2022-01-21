<template>
  <div class="mycard">
    <div class="layout-card">
      <div class="img-container m-3">
        <img v-if="poster" :src="image" :alt="title">
        <img v-else src="data:image/png;base64,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" :alt="title">
      </div>
      <div class="hover">
        <div class="info d-flex justify-content-between align-items-center">
          <div class="container-title">
              <span class="title mb-2">{{title}}</span>
          </div>
          <div v-show="title !== original" class="original-title mb-2">
              <span>Titolo originale:</span>
              <span class="original-title">{{original}}</span>
          </div>
          <div class="plot">
              <p>{{plot}}</p>
          </div>
          <span class="mb-2">Lingua: <i :class="'flag flag-' + getFlags(lang)"></i></span>
          <span>Voto: {{arrNum(vote)}}</span>
          <div class="d-flex">
            <i v-for="n in 5" :key="n" :class="(n <= arrNum(vote)) ? 'fas fa-star' : 'far fa-star'"
            />
          </div>
        </div>
      </div>
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
    'poster',
    'plot',
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
        case 'hi':
          return 'in';
        default:
          return lang;
      }
    },
    arrNum(vote) {
      return Math.round(vote / 2);
    }
  }
}
</script>

<style lang="scss">
.mycard {
  padding: 0.5em 1em;
  .layout-card {
    position: relative;
    color: white;
    text-align: center;
		display: flex;
		flex-direction: column;
		align-items: center;
		height: 100%;
    border: 1px solid #DC1A28;
    border-radius: 10px;
    .img-container {
      height: 300px;
      overflow: hidden;
      img {
      height: 100%;
      border-radius: 10px;
      }
    }
    .hover {
      display: none;
      position: absolute;
      background-color: #666565;
      opacity: 0.9;
      height: 100%;
      width: 100%;
      border-radius: 10px;
      .info {
        overflow: auto;
        height: 100%;
        padding: 0.3em;
        opacity: 1;
        flex-direction: column;
        .plot {
          font-size: 0.7em;
        }
        span {
          font-size: 0.9em;
          display: block;
        }
        .title {
          font-size: 1.2em;
          }
        .original-title {
          font-size: 1.1em;
        }
      }
    }
  }
  .layout-card:hover .hover {
    display: block;
  }
}
</style>