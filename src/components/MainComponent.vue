<template>
  <div>
   <h1>TITOLO</h1>
   <div v-for="(disco, i) in listaDischi" :key="i">
  {{disco.author}}
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
  props: {
    msg: String
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((res) =>{
      console.log(res.data)
      this.listaDischi = res.data
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import '../styles/general.scss';
h1{
  text-align: center;
}
</style>
