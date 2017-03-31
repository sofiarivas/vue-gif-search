<!-- Component Template -->
<template>
    <div class="cat-search-container">
      <span class="cat-search-title"> {{question}}</span><span class="cat-search-query">{{query}}</span>
      <input v-model="query" v-bind:placeholder="placeholder" class="cat-search-query-input">
      <button @click.stop="getGifSearch" class="cat-search-button">Buscar</button>
    </div>
</template>

<!-- Component Script -->
<script>
  export default {
    name: 'cat-search',
    props: {
      question: '',
      placeholder: ''
    },
    data: function () {
      return {
        query: ''
      }
    },
    methods: {
      getGifSearch () {
        console.log('searching')
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
  	margin: 20px auto;
  	border-top: 1px solid grey;
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
    margin-top: 20px;
  }
  .cat-search-button:active {
    background-color: hotpink;
    font-weight: bold;
    color: white;
    outline: none;
  }
</style>