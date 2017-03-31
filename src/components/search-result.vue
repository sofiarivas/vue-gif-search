<!-- Component Template -->
<template>
    <div class="cat-search-container">
      <p>Resultado</p>
      <img v-bind:src="imageSource">
    </div>
</template>

<!-- Component Script -->
<script>
  export default {
    name: 'search-result',
    props: {
      imageSource: ''
    }
  }
</script>

<!-- If necessary, component styles -->
<style scoped>

</style>