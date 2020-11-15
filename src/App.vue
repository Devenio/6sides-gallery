<template>
  <div class="container">
    <h1 id="gallery-header">Gallery</h1>
    <h4>this is nimo <small>Gallery</small>...</h4>
    <hr>
    <br><br>
    <app-gallery></app-gallery>
  </div>
</template>

<script>
import gallery from './components/gallery.vue'

export default {
  components: {
    appGallery: gallery
  }
}
</script>

<style lang="scss">
@import './scss/mixins';
@import url('https://fonts.googleapis.com/css2?family=Lobster&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Lobster&family=Roboto&display=swap');

.container{
  text-align: center;

  hr{
    width: 200px;
    color: red;
  }
  #gallery-header ,
  small{
    font-family: 'Lobster', cursive;
  }
  h4{
    font-family: 'Roboto', sans-serif;
  }
}
</style>
