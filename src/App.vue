<template>
  <div id="app">
    <header-dischi />
    <main-dischi />
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
  }
}
</script>

<style lang="scss">
$primary: #1e2d3b;
$secondary: #2e3a46;
@import "../node_modules/bootstrap/scss/bootstrap";
</style>
