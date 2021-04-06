<template>
  <div class="search-bar">
    <span class="title" v-html="title"></span><br>
    <span class="desc" v-html="desc"></span><br><br>
  </div>
</template>

<script>
export default {
  name: 'SingleResult',
  props: {
    title: String,
    desc: String
  },
  data: function() {
    return {
    }
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.title{font-size:17px;color: blue;}
.desc{font-size: 13px;color: green;}
</style>
