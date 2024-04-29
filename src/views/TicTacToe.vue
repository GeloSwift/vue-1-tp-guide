<script setup lang="ts">

    import { ref } from 'vue';
    import Cellule from '@/components/Cell.vue';


    const shapes = ref([
        ['empty', 'empty', 'empty'],
        ['empty', 'cross', 'empty'],
        ['empty', 'empty', 'empty']
    ])

    function reset(){
        for (let row = 0; row < 3; row++) {
            for (let col = 0; col < 3; col++) {
                shapes.value[row][col] = 'empty'
            }
        }
    }



</script>


<template>

    <h1>Tic Tac Toe</h1>
    <button @click="reset()"> reset </button>
    <div class="wrapper">
        <template v-for="row in [0,1,2]">
            <template v-for="col in [0,1,2]">
                <Cellule v-model:shape="shapes[row][col]" class="tttCell"></Cellule>
            </template>
        </template>
    </div>

</template>


<style scoped>
    .wrapper {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
    }

    .tttCell {
        border:solid
    }


</style>