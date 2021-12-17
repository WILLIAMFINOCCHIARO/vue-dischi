<template>
  <div class="search-bar">
    <form action="">
      <input type="text" class="mt-3 form-control" placeholder="Search song" v-model="searchText" >
      <button class="text-danger fs-4 fw-bold my-2" @click.prevent ="$emit('search',searchText)">Search</button>
      <button class="text-danger fs-4 fw-bold" @click.prevent="$emit('search','')">Reset</button>
    </form>
  </div>
</template>

<script>
export default {
  name:"SearchBar",
  data() {
    return {
      searchText:''
    }
  }

}
</script>

<style lang="scss" scoped>

</style>