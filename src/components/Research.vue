<template>
  <div class="Research">
    <h2>PLEASE SEARCH ME NOW!!!</h2>
    <h3>{--- ENGLISH ONLY ---}</h3>
    <form v-on:submit.prevent="getResult(query)">
      <input type="text" placeholder="SEARCH ME!" v-model="query" />
    </form>
    <div class="results" v-if="results">
      <div v-for="result in results" v-bind:key="result">
          <img v-bind:src="result.links[0].href" />
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Research',
  data () {
    return {
      msg: 'ReSearch',
      query: '',
      results: ''
    }
  },
  methods: {
      getResult(query) {
        axios.get('https://images-api.nasa.gov/search?q=' + query + '&media_type=image').then( response => {
            console.log(response.data.collection.items);
            this.results = response.data.collection.items;
        });
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.results img {
    height: 300px;
    margin: 10px;
}
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>