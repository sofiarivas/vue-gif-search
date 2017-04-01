<!-- Component Template -->
<template>
    <div class="cat-search-container">
      <span class="cat-search-title"> {{question}}</span><span class="cat-search-query">{{query}}</span>
      <input v-model="query" v-bind:placeholder="placeholder" class="cat-search-query-input">
      <button @click.stop="getGifSearch(query)" class="cat-search-button">Buscar</button>
      <search-tile v-if="gifSearchResult.length > 0" :gifs-data="gifSearchResult"></search-tile> 
    </div>
</template>

<!-- Component Script -->
<script>
import searchTile from './search-result.vue'
  export default {
    name: 'cat-search',
    components: {
      searchTile
    },
    props: {
      question: {
        type: String,
        default: ''
      },
      placeholder: {
        type: String,
        default: ''
      }
    },
    data: function () {
      return {
        query: '',
        gifSearchResult: {
          type: Array,
          default: () => {
            return []
          }
        }
      }
    },
    methods: {
      getGifSearch (query) {
        this.gifSearchResult = []
        {
        // GET /someUrl
        this.$http.get(`https://api.giphy.com/v1/gifs/search?q=${query}&api_key=dc6zaTOxFJmzC`).then(response => {

          
          // get body data
          this.gifSearchResult = response.body.data
        }, response => {
            // error callback
          });
        }
      }
    }
  }
</script>

<!-- If necessary, component styles -->
<style scoped>

  button {
    outline: none;
  }

  .cat-search-container {
  	margin: 20px auto 0;
  	border-top: 1px solid lightgrey;
  	width: 85%;
  }

  .cat-search-title {
    display: inline-block;
    padding: 20px 2px;
  }

  .cat-search-query {
    color: hotpink;
    font-weight: bold;
  }

  .cat-search-query-input {
    display: block;
    width: 50%;
    margin: auto;
    border: 1px solid hotpink;
    font-size: 14px;
    border-radius: 2px;
    color: hotpink;
  }

  .cat-search-button {
    background-color: aquamarine;
    color: grey;
    padding: 10px 30px;
    border-radius: 2px;
    border: 0;
    margin: 20px;
  }
  .cat-search-button:active {
    background-color: hotpink;
    font-weight: bold;
    color: white;
    outline: none;
  }
</style>