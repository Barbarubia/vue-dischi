<template>
<div class="d-flex align-items-stretch">
  <div class="w-100 bg-secondary text-center p-3">
    <img class="w-100" :src="discoData.poster" :alt="discoData.title">
    <h5 class="text-white text-uppercase">{{ discoData.title }}</h5>
    <h6>{{ discoData.author }}</h6>
    <h6>{{ discoData.year }}</h6>
  </div>
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
