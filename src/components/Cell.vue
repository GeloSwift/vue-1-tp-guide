<script setup lang="ts">

    import { Icon } from '@iconify/vue'

    const model = defineModel<string>('shape', {required:true})


    const SHAPES = ['circle', 'cross', 'empty']

    function switchShape() {
        const currentIndex = SHAPES.indexOf(model.value)
        model.value = SHAPES[(currentIndex + 1) % SHAPES.length]
    }

</script>


<template>
    
    <div @click="switchShape" class="cell">
        <Icon v-if="shape=='cross'"         icon="radix-icons:cross-1" width="10em" />
        <Icon v-else-if="shape=='circle'"   icon="radix-icons:circle" width="10em" />
    </div>

</template>


<style scoped>

    .cell {
        border: dotted 1px rgb(0, 0, 0);
        min-width: 11em;
        min-height: 11em;
        display: flex;
        justify-content: center;
        align-items: center;
    }

</style>