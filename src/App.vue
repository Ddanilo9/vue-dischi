<template>
  <div id="app">
    <HeaderComponent @find="onSearch"/>
    <MainContent :find="findProp"></MainContent>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainContent from './components/MainContent.vue'

export default {
  name: 'App',
  data(){
    return{
      findProp:''
    }
  },
  components: {
    HeaderComponent,
    MainContent,
},
methods: {
  onSearch(data) {
    // console.log('avviso')
   this.findProp= data
  }
}
}
</script>

<style lang="scss">
  @import '../src/styles/general.scss';
#app{
  background-color: rgba(30,45,59,255);
}
</style>
