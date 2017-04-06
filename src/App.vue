<template>
  <div id="app">
    <Search v-on:SearchRequested="handleSearch"></Search>
    <Film v-bind:films=films></Film>
  </div>
</template>

<script>

import Search from './components/search.vue'
import Film from './components/film.vue'

export default {
  name: 'app',
  components:{Search , Film},
  data(){
    return{
          films:[]
     }
  },
  methods:{
    handleSearch(query){
      this.films=[];
     fetch('http://www.omdbapi.com/?t='+query)
  .then((res) => { return res.json() } )
  .then((res) =>{ 
    this.films=res;
    console.log(this.films.Error)
  })
    }
    },
    created(){
        fetch('http://www.omdbapi.com/?t=Fast')
        .then((res) => { return res.json() } )
        .then((res) =>{ 
          this.films=res;
        console.log(this.films.Error)
        })
    }
  }

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

}
</style>
