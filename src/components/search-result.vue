<!-- Component Template -->
<template>
  <div>
      <img v-for="gif in gifsData" :src="gif.images.fixed_width.url" class="search-item">
  </div>
</template>

<!-- Component Script -->
<script>
  export default {
    name: 'search-tile',
    props: {
      gifsData: {
        type: Array,
        default: () => {
          return []
        }
      }
    }
  }
</script>

<!-- If necessary, component styles -->
<style scoped>

  .search-item {
    margin: 10px;
  }

</style>