<template>
  <div id="app" class="bg-primary">
    <header-dischi @sendSelectedGenre="setSelectedGenre" @sendInputAuthor="searchInputAuthor" :genres-options="arrGenres"/>
    <main-dischi @send-data="setArrData" :string-filter-genre="selectedGenre" :string-input-author="inputAuthor"/>
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
      selectedGenre: '',
      inputAuthor: '',
      arrDischi: []
    }
  },
  computed: {
    arrGenres () {
      console.log([...new Set(this.arrDischi.map(element => element.genre))])
      return [...new Set(this.arrDischi.map(element => element.genre))]
    }
  },
  methods: {
    setArrData (arrDischiPassato) {
      this.arrDischi = arrDischiPassato
    },
    setSelectedGenre (genre) {
      this.selectedGenre = genre
    },
    searchInputAuthor (searchText) {
      this.inputAuthor = searchText
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
