<script setup lang="ts">

    import Cell from "@/components/Cell.vue"
    import { ref } from 'vue'

    const cellShape = ref('circle')

    
</script>

<template>
    
    <h1>Page test d'un composant cellule</h1>
    <Cell v-model:shape="cellShape"></Cell>
    <div> 
        Dans le parent la cellule contient : {{ cellShape }}
        <button @click="cellShape='circle'"  >Circle</button>
        <button @click="cellShape='cross'"   >Cross</button>
    </div>

</template>