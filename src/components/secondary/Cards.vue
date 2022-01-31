<template>
  <div class="d-flex mycontainer">
      <SingleCard 
      v-for= "(elementi , index) in artistiLista"
      :key="index"
      :info="elementi"
      />

  </div>
</template>

<script>
import axios from "axios";
import SingleCard from "./SingleCard.vue";

export default {
    name:'Cards',
    components: {
        SingleCard

    },
    created(){
        this.getArtisti();
    },
    data() {
        return{
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            artistiLista: []
        }

    },
    methods:{
        getArtisti(){
            axios
                .get(this.apiURL)
                .then((personaggi) =>{
                    console.log(personaggi.data.response);
                    this.artistiLista = personaggi.data.response ;
                    
                })
                .catch((errore) => {
                    document.writeln('sorry, there is an error'+ errore)
                });

        }
        
    }

}
</script>

<style>

</style>