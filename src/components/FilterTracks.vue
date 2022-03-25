<template>
  <div>
    <select @change="filter($event)" name="filter-genre" id="filter-genre">
      <option value="">Seleziona un genere</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'FilterTracks',
  methods: {
    filter (event) {
      console.log(event.target.value)
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
