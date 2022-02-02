<template>
<div class="user  text-center m-2">
    <img :src="info.poster" alt="">
    <div class="song">{{info.title}}</div>
    <div class="artist">{{info.author}}</div>
    <div class="artist">{{info.year}}</div>
    
</div>
  
</template>

<script>

export default {
    name:'SingleCard',
    props:{   
        info: Object      
    },

}
</script>

<style lang='scss' scoped>


.user{
  width:180px ;
  min-height:280px;
  background-color: rgb(59, 59, 72);
  img{
    width: 160px;
    margin-top: 10px;
  }
  .song{
    color: white;
    font-weight: bold;
    font-size: 21px;
    margin-bottom: 10px;
    margin-top: 15px;

  }
  .artist{
    color: rgb(95, 92, 92);
    font-size: 11px;
  }
}

</style>