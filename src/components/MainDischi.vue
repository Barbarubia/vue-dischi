<template>
  <main class="py-5">
    <div class="container-sm container-md container-xl">
      <div v-if="arrDischi == null" class="row bg-secondary justify-content-center text-center dd_splashpage p-5">
        <font-awesome-icon icon="fa-solid fa-compact-disc" class="dd_disco text-white" spin />
        <h1 class="text-white mt-5">Download Tracks...</h1>
      </div>
      <div v-else class="row row-cols-sm-1 row-cols-md-3 row-cols-xl-5 g-3">
        <card-disco
          v-for="disco in filterGenre()"
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
  filteredDischi: '',
  components: {
    CardDisco
  },
  props: {
    stringFilterGenre: String,
    stringInputAuthor: String
  },
  data () {
    return {
      arrDischi: null
    }
  },
  methods: {
    filterGenre () {
      if (this.stringFilterGenre === '' && this.stringInputAuthor === '') {
        return this.arrDischi
      } else if (this.stringFilterGenre !== '' && this.stringInputAuthor === '') {
        return this.arrDischi.filter(disco => disco.genre === this.stringFilterGenre)
      } else if (this.stringFilterGenre === '' && this.stringInputAuthor !== '') {
        return this.arrDischi.filter(disco => disco.author.toLowerCase().includes(this.stringInputAuthor.toLowerCase()))
      } else {
        return this.arrDischi.filter(disco => disco.genre === this.stringFilterGenre && disco.author.toLowerCase().includes(this.stringInputAuthor.toLowerCase()))
      }
    }
  },
  created () {
    setTimeout(() => {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((risposta) => {
          // console.log(risposta)
          this.arrDischi = risposta.data.response
          // console.log(this.arrDischi)
        })
    }, 3000)
  }
}
</script>

<style lang="scss" scoped>
// main {
//   height: calc(100vh - 5rem);
// }
.dd_splashpage .dd_disco {
  font-size: 200px;
}
</style>
