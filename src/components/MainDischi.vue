<template>
  <main class="bg-primary py-5">
    <div class="container-sm container-md container-xl">
      <div class="row">
        <card-disco
          v-for="disco in arrDischi"
          :key="disco.title"
          :disco-data="disco"
        />
      </div>
    </div>
  </main>
</template>

<script>
import CardDisco from './CardDisco.vue'
import axios from 'axios'

export default {
  name: 'MainDischi',
  data () {
    return {
      arrDischi: null
    }
  },
  components: {
    CardDisco
  },
  created () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((risposta) => {
        // console.log(risposta)
        this.arrDischi = risposta.data.response
        console.log(this.arrDischi)
      })
  }
}
</script>

<style lang="scss" scoped>
main {
  height: calc(100vh - 7rem);
}
</style>
