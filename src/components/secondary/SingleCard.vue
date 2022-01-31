<template>
<div class="user  text-center">
    <img :src="info.poster" alt="">
    <div class="song">{{info.title}}</div>
    <div class="artist">{{info.author}}</div>
    <div class="year">{{info.year}}</div>
    
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
  img{
    width: 160px;
    height: 190px;
  }
}

</style>