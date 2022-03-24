<template>
  <div>
    <img :src="discoData.poster" :alt="discoData.title">
    <h3>{{ discoData.title }}</h3>
    <span>{{ discoData.author }}</span>
    <span>{{ discoData.year }}</span>
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

</style>
