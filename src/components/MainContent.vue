<template>
    <div>
     <div class="container grid">
        <div v-for="(disco, i) in selectG" :key="i" class="card">
          <CardComponent :info="disco"></CardComponent>
        </div>
     </div>
    </div>
  </template>
  
  <script>
  import axios from "axios"

  import CardComponent from './CardComponent.vue'
  
  export default {
    name: 'MainContent',
    props: {
      find:{
        type: String,
        default: ''
      }
    },
    data(){
      return{
        listaDischi: [],
        // genereSelezionato:''
      }
    },
    computed: {
      selectG (){
        return this.listaDischi.filter((el) => {
          let genere = el.genre.toLowerCase()
          let find = this.find

          if (genere.includes(find)) {
            return true
          }
          return false

        })
      }
    },
    created() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((res) =>{
        console.log(res.data)
        this.listaDischi = res.data.response
      });
    },
    components: {
        CardComponent
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
    @import '../styles/general.scss';
  .grid{
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-column-gap: 40px;
    grid-row-gap: 15px;
        .card{
            background-color: rgba(46,58,70,255);
            color: white;
            padding: 15px;
        }
  }
  </style>
  