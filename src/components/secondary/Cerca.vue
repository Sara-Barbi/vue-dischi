<template>
<span class="d-flex align-items-center">
    
    <select
        name= "filter-genre"
        id="filter-genre"
        v-model="genreFilter"
        @change='cambioSelect' 
        
       >
        <option v-for="genere in listageneri" :key="genere" :value="genere">{{genere}}</option>
    </select>
   
</span>
  

</template>

<script>
export default {
    name: 'Cerca',
    data (){
        return{
            genreFilter:"",
        }
    },
        
    props:{
        listageneri: Array
        
    },
    methods:{

        cambioSelect: function(){
           this.$emit('cambiato' ,this.genreFilter)
        
        }
    },
    

}
</script>

<style>

</style>