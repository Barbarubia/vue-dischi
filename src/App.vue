<template>
  <div id="app" class="bg-primary">
    <header-dischi @sendSelectedGenre="setSelectedGenre" />
    <main-dischi :stringa-filtro="selectedGenre"/>
  </div>
</template>

<script>
import HeaderDischi from './components/HeaderDischi.vue'
import MainDischi from './components/MainDischi.vue'

export default {
  name: 'App',
  components: {
    HeaderDischi,
    MainDischi
  },
  data () {
    return {
      selectedGenre: ''
    }
  },
  methods: {
    setSelectedGenre (genre) {
      this.selectedGenre = genre
    }
  }
}
</script>

<style lang="scss">
$primary: #1e2d3b;
$secondary: #2e3a46;
@import "../node_modules/bootstrap/scss/bootstrap";

html {
  background-color: $primary;
}
</style>
