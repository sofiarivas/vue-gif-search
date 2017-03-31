<!-- Component Template -->
<template>
  <div>
      <video width="320" height="240" autoplay v-for="gif in gifsData" class="gif-tile">
      <source :src="gif.images.downsized_small.mp4" type="video/mp4">
        Tu navegador no soporta la etiqueta de video HTML, no gifs for you my friend.
    </video>
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
  .gif-tile {
    margin: 10px;
  }
</style>