<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <SearchBar @start-search="doSearch(event)"/>
  <ResultSet :resultsList="searchResult"/>
</template>

<script>
import SearchBar from './components/SearchBar.vue'
import ResultSet from './components/ResultSet.vue'
import axios from 'axios';

export default {
  name: 'App',
  components: {
    SearchBar,
    ResultSet
  },
  data: function() {
    return {
      searchResult: [
        {title:"Hello world", desc: "First <b>result</b> item"},
        {title:"second", desc: "Second result item"},
        {title:"three", desc: "Third result item"},
      ]
    }
  },
  methods: {
    doSearch : function(str) {
      var that = this;
      console.log("Search to be implemented: ",str );
      console.log(that)
      /*axios.get('url')   // url should be valid api
        .then(function(response){
          console.log(response);
          that.searchResult = response.data.value;
        }).catch(function(error){
          console.error(error);
        }).then(function(){
          //always excuted
        })*/
      axios.get(`http://jsonplaceholder.typicode.com/posts`)
        .then(response => {
          // JSON responses are automatically parsed.
          console.log(response.data)
        })
        .catch(e => {
          this.errors.push(e)
        })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
