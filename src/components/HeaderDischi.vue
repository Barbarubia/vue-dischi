<template>
  <header class="bg-secondary d-flex justify-content-between px-5 py-3">
    <a href="#"><img class="h-100" src="../assets/img/logo.png" alt="logo"></a>
    <div class="align-self-center">
      <label for="filter-author">
        <input @keyup="$emit('sendInputAuthor', searchText)" v-model="searchText" type="text" name="filter-author" id="filter-author" placeholder="Search by author">
      </label>
      <select @change="$emit('sendSelectedGenre', selectedGenre($event))" name="filter-genre" id="filter-genre">
        <option value="">Select a genre</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderDischi',
  data () {
    return {
      searchText: ''
    }
  },
  methods: {
    selectedGenre (option) {
      // console.log(option.target.value)
      return option.target.value
    }
  }
}
</script>

<style lang="scss" scoped>
header {
  height: 7rem;
}
</style>
