<template>
  <main class="py-5">
    <div class="container-sm container-md container-xl">
      <div v-if="arrDischi == null" class="row bg-secondary justify-content-center text-center dd_splashpage p-5">
        <img src="../assets/img/loading.gif" alt="loading">
        <!-- Icona da usare dopo aver importato font awesome -->
        <!-- <i class="fa-solid fa-compact-disc"></i> -->
        <h1 class="text-white mt-5">Download Tracks...</h1>
      </div>
      <div v-else class="row justify-content-center">
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
    setTimeout(() => {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((risposta) => {
          // console.log(risposta)
          this.arrDischi = risposta.data.response
          // onsole.log(this.arrDischi)
        })
    }, 3000)
  }
}
</script>

<style lang="scss" scoped>
// main {
//   height: calc(100vh - 5rem);
// }
.dd_splashpage img {
  width: 200px;
}
</style>
