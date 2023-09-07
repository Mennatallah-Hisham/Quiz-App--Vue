<script setup>
import {ref,watch} from"vue";
import q from "./data/quizes.json"
import Card from "./components/Card.vue";
import {RouterView} from "vue-router"
const quizes =ref(q)
const search=ref("");


watch(search,()=>{
  console.log("hello frim watch")
  quizes.value=q.filter(quiz=>quiz.name.toLowerCase().includes(search.value.toLowerCase()));

})
</script>
<template>
<div class="container">
  <RouterView/>


  <header>
    <h1> quiz app</h1>
 
    <form>
      <input v-model.trim="search" type="text"/>
    </form>

  </header>
  
  <div class="options-container">
    <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
  

   

  </div>

</div>
</template>

<style scoped>
.options-container{
  border:1px solid black;
  display: flex;
  flex-wrap: wrap;
  gap:1rem;

}


</style>