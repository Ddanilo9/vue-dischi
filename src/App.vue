<template>
  <div id="app">
    <HeaderComponent/>
    <MainContent></MainContent>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainContent from './components/MainContent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainContent,
}
}
</script>

<style lang="scss">
  @import '../src/styles/general.scss';
#app{
  background-color: rgba(30,45,59,255);
}
</style>
