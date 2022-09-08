<template>
  <div>
   <h1>VUE-DISCHI</h1>
   <label for="genere">Choose a genre</label>
    <select name="genere" id="genere">
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="metal">Metal</option>
      <option value="jazz">Jazz</option>
    </select>
  <br><br>
  <input type="submit" value="Submit" @click="$emit('find', find)">
   </div>
</template>

<script>


export default {
  name: 'MainContent',
  data(){
    return {
      find: ''
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
h1{
  text-align: center;
  padding: 20px 0;
  color: white;
}
</style>
