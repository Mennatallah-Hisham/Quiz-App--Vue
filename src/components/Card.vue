<script setup>
defineProps(['quiz'])
</script>
<template>

    
    <article class="card">
        <img :src="quiz.img" alt="cover image"/>
  
        <h2>{{quiz.name}}</h2>
        <p> {{quiz.questions.length}} questions</p>
  
      </article>
</template>

<style scoped>
.card{
    width:22rem;
    padding:1rem;
    border:1px solid red;
    overflow:hidden;
    border-radius: 2rem;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
  }
  .card img{
    max-width: 100%;
    display: block;
  }</style>