<template>
  <div id="app">
    <h1>GIFs de viernes<img class="vue-logo" src="https://vuejs.org/images/logo.png"></h1>
    <span>Gifs para alegrarse la vida</span>
    <cat-search :question="'¿A mi viernes le hace falta?'" :placeholder="'Netflix & chill'"></cat-search>
    <search-result></search-result>
    <img class="gif-splash" src="https://media.giphy.com/media/3o7btV1sSvBaaSAQKc/giphy.gif">
    <span class="build-with-vue"> Build with </span><a class="vue-link" href="https://vuejs.org">Vue.js</a>.
  </div>
</template>

<script>
import catSearch from './components/cat-search.vue'
import searchResult from './components/search-result.vue'

export default {
  name: 'app',
  components: {
    catSearch,
    searchResult
  },
  data () {
    return {
      msg: 'Busca los mejores Gifs de gatos'
    }
  },
  props: {
    imageSource: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

h1 {
  font-family: 'Gochi Hand', cursive;
  margin-top: 30px;
  color: hotpink;
}

a {
  color: #42b983;
}

.vue-logo {
  width: 20px;
  height: 20px;
  margin-left: 5px;
}

.gif-splash {
  width: 400px;
  height: 400px;
  margin: auto;
  display: block;
}

.build-with-vue {
  font-size: 11px;
}

.vue-link {
  font-size: 12px;
  font-weight: bold;
  color: #2c3e50;
}

#app {
  margin: 0;
}

</style>
