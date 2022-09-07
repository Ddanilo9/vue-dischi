<template>
    <div>
     <div class="container grid">
        <div v-for="(disco, i) in listaDischi" :key="i">
          <img src="" alt="">
          <h3>{{disco.title}}</h3>
          <div>{{disco.author}}</div>
          <div>{{disco.year}}</div>
        </div>
     </div>
    </div>
  </template>
  
  <script>
  import axios from "axios"
  
  export default {
    name: 'MainContent',
    data(){
      return{
        listaDischi: []
      }
    },
    created() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((res) =>{
        console.log(res.data)
        this.listaDischi = res.data.response
      });
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
    @import '../styles/general.scss';
  .grid{
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-column-gap: 10px;
    grid-row-gap: 10px;
  }
  </style>
  