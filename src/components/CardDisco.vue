<template>
  <div class="bg-secondary text-center col-sm-12 col-md-3 col-xl-2 mx-2 p-3 gy-3">
    <img class="w-100" :src="discoData.poster" :alt="discoData.title">
    <h5 class="text-white text-uppercase">{{ discoData.title }}</h5>
    <h6>{{ discoData.author }}</h6>
    <h6>{{ discoData.year }}</h6>
  </div>
</template>

<script>
export default {
  name: 'CardDisco',
  props: {
    discoData: Object
  }
}
</script>

<style lang="scss" scoped>
h6 {
  color: #787b7f;
}
</style>
