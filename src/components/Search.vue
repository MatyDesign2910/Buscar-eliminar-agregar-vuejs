<template>
    <div id="search-container">
        <input type="text" v-model="query" placeholder="Buscar producto" v-on:input="$emit('query-change', query)">
    </div>
</template>

<script>

export default {
  name: "Search",
  data() {
      return {
          query: ''
      }
  }
}

</script>

<style scoped>
    #search-container {
        width:300px;
        margin: 0 auto;
    }
    #search-container input {
        padding: 10px;
        width:100%;
        outline: none;
    }
    @media (max-width: 767px) {
        #search-container {
            width: 100%;
        }
    }
</style>