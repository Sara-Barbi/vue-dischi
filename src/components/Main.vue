<template>
  <div class="hello">
    <div class="container-fluid">
     
        <Cards />
         
     
    </div>
  </div>
</template>

<script>
import Cards from'./secondary/Cards.vue';
export default {
  name: 'Main',
  components:{
    Cards
  },
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../assets/style/variables.scss';

.container-fluid{
  background-color:$mainBack;
}

</style>
