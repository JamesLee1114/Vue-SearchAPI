<template>
  <div class="result-set">
    This is the result set, and it's length is {{countResults()}}
    <SingleResult v-for="(res,index) in resultsList" :title="res.title" :desc="res.desc" :key="index"/>
  </div>
</template>

<script>
import SingleResult from './SingleResult'
export default {
  name: 'ResultSet',
  props: {
    resultsList: []
  },
  components: {
    SingleResult
  },
  data: function() {
    return {
    }
  },
  methods: {
    countResults: function(){
      return this.resultsList.length;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
