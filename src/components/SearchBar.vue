<template>
  <div class="search-bar">
    Search: <input type="text" v-model = "selfdata">
    <button @click="search()">Search</button>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    msg: String
  },
  data: function() {
    return {
      selfdata : "Enter search"
    }
  },
  methods: {
    search: function(){
      this.$emit("start-search", this.selfdata)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input {border-radius: 5px; border: 1px solid grey;}
</style>
