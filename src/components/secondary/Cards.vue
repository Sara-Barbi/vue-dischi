<template>
  <div class="d-flex mycontainer justify-content-center">
      <SingleCard 
      class="mt-3"
      v-for= "(elementi , index) in albumFiltrati"
      :key="index"
      :info="elementi"
      />
      <Cerca
        @cambiato="filtraAlbum"
        :listageneri="listaGeneri" 
        class='laPosition'
        
     />

  </div>
</template>

<script>
import axios from "axios";
import Cerca from "./Cerca.vue";
import SingleCard from "./SingleCard.vue";


export default {
    name:'Cards',
    components: {
        SingleCard,
        Cerca


    },
    created(){
        this.getArtisti();
        
    },
    data() {
        return{
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            artistiLista: [],
            genre:"",

            
        }
    

    },
    methods:{
        filtraAlbum: function(payloadEmit){
            this.genre = payloadEmit; 
           
        },

        getArtisti: function(){
            axios
                .get(this.apiURL)
                .then((personaggi) =>{
                    console.log(personaggi.data.response);
                    this.artistiLista = personaggi.data.response ;
                  
                    
         
                    
                })
                .catch((errore) => {
                    document.writeln('sorry, there is an error'+ errore)
                });

        },
        trasportaFiglio : function(){
           this.$emit('cambiare' ,this.listaGeneri())
        }
    },
    computed:{
        listaGeneri(){
            const generiFiltrati = [];
            this.artistiLista.forEach(element =>{
                if(!generiFiltrati.includes(element.genre)){
                    generiFiltrati.push(element.genre)
                }
            });
           
            return generiFiltrati
        },

        albumFiltrati(){
        return this.artistiLista.filter((elementi)=>{
          return ( elementi.genre.toLowerCase() == this.genre.toLowerCase()) || (this.genre == "")
          });
        }
    },
  
}
</script>

<style>

</style>