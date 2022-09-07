<template>
  <div>
   <h1>VUE-DISCHI</h1>
   </div>
</template>

<script>


export default {
  name: 'MainContent',

  props: {
    msg: String,
  },
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import '../styles/general.scss';
h1{
  text-align: center;
  padding: 20px 0;
  color: white;
}
</style>
