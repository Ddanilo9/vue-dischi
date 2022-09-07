<template>
    <div>
     <div class="container grid">
        <div v-for="(disco, i) in listaDischi" :key="i" class="card">
            <div class="info-card">
                <img :src="disco.poster" alt="">
                <h3>{{disco.title}}</h3>
                <span>{{disco.author}}</span>
                <span>{{disco.year}}</span>
            </div>
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
        .card{
            background-color: rgba(46,58,70,255);
            color: white;
            padding: 15px;
                .info-card{
                    display: flex;
                    flex-direction: column;
                    align-items: center;

                    h3{
                        padding: 10px 0;
                        text-align: center;
                    }
                    span{
                        padding: 2px 0;
                    }
                }
        }
        img{
            max-width: 100%;
            cursor: pointer;
        }
  }
  </style>
  