<template>
  <header class="bg-secondary d-flex justify-content-between px-5 py-3">
    <a href="#"><img class="h-100" src="../assets/img/logo.png" alt="logo"></a>
    <filter-tracks class="align-self-center" />
  </header>
</template>

<script>
import FilterTracks from './FilterTracks.vue'

export default {
  name: 'HeaderDischi',
  components: {
    FilterTracks
  }
}
</script>

<style lang="scss" scoped>
header {
  height: 7rem;
}
</style>
