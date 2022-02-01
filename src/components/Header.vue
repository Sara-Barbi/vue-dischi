<template>
  <div class="hello">
    <div class="container-fluid">
      <div class="row">
        <div class="col-9 ">
          <img src="../assets/img/spotify-logo.png" alt="">
        </div>
        <div class="col-3 d-flex align-content-center">
          <Cerca />
        </div>
       </div>
    </div>
  </div>
</template>

<script>
import Cerca from "./secondary/Cerca.vue";

export default {
  name: 'Header',
  components:{
    Cerca
  },
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../assets/style/variables.scss';





div{
  
  min-height: 65px;
  background-color: $headerBack;

   img{
  width: $logoWidth;
  margin-left: $logoml;
  float:$logoPosition;
  background: $logoBack;
  border-radius:$circleBack;
}


}



















</style>

