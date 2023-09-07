<script setup>
import { useRoute } from 'vue-router';
import { ref } from 'vue';
import q from "../data/quizes.json";


const route= useRoute();
const quiz = q.filter((quiz)=>quiz.id===parseInt(route.params.id));

</script>

<template>

    <h1> questions</h1>
    
    <h2>{{route.params.id}}</h2>
    <p>
        {{ quiz }}
    </p>
</template>