<template>
<span class="d-flex align-items-center">
    <select 
        name="" 
        id=""
        @click="$emit('search','inputText')">
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
    </select>
</span>
  

</template>

<script>
export default {
    name: 'Cerca',
    data (){
        return{
            
        }
    }

}
</script>

<style>

</style>