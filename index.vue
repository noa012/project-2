<template> 
  <div id="app">
    <div class="container">
      <div class="moviesonscreeen">
          <li v-for="movie of movies" :key="movie.id">{{movie.original_title}}</li>
      </div>
      <div>
        <button @click="fetch">click me</button>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
let url="https://api.themoviedb.org/3/search/movie?api_key=ddac2a9248a58d23cea75a9609c45bbc&query=jack"
export default {
  data(){
    return{
      movies:[]
    }
  },
  methods:{
    async fetch(){
      this.movies = await axios.get(url).then(res=>res.json).catch((e)=>{console.log(e)})
      console.log("data:",movies)
    }
  }
}
</script>

<style>

</style>
