<template>
      <div class="info-card">
                <img :src="info.poster" alt="">
                <h3>{{info.title}}</h3>
                <span>{{info.author}}</span>
                <span>{{info.year}}</span>
            </div>
  </template>
  
  <script>
  
  
  export default {
    name: 'CharacterComponent',
  
    props: {
      info: Object
    },
   
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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
    img{
    max-width: 100%;
    cursor: pointer;
    aspect-ratio: 1/1;
    }
 
  </style>
  