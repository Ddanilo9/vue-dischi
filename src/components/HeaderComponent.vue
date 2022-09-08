<template>
  <header>
   <h1>VUE-DISCHI</h1>
   <label for="genere">Choose a genre</label>
    <select v-model="cerca" @change="$emit('find', cerca)" name="genere" id="genere">
      <option value="">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="metal">Metal</option>
      <option value="jazz">Jazz</option>
    </select>
   </header>
</template>

<script>

// $emit('find', find)
export default {
  name: 'MainContent',
  data(){
    return {
      cerca: ''
    }
  },
  methods: {
    test() {
      console.log(this.cerca)
    }
  },
  props: {
    msg: String,
  },
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import '../styles/general.scss';
  header{
    display: flex;
    flex-direction: column;
    align-items: center;
    color: white;
    margin-bottom: 10px;
      h1{
        text-align: center;
        padding: 20px 0;
        
      }
  }

</style>
