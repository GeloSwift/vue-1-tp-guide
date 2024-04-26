<script setup lang="ts">
    import { Icon } from '@iconify/vue'
    import { ref } from 'vue'

    const shape = ref('cross')

    function switchShape() {
        shape.value = (shape.value=='circle' ? 'cross' : 'circle')
    }
    

</script>


<template>
    
    <div @click="switchShape" class="cell">
        <Icon v-if="shape=='cross'" icon="radix-icons:cross-1" width="10em" />
        <Icon v-else                icon="radix-icons:circle" width="10em" />
    </div>

</template>


<style>

    .cell {
        border: dashed 1px pink;
    }

</style>