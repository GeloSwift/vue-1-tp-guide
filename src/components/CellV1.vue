<script setup lang="ts">
    import { Icon } from '@iconify/vue'
    import { ref, watch } from 'vue'

    const emit = defineEmits<{
        change : [shape : string]
    }>()

    const props = defineProps<{
        shapeInit : string
    }>()

    watch(props, () => shape.value = props.shapeInit)

    const shape = ref(props.shapeInit)

    const SHAPES = ['circle', 'cross', 'empty']

    function switchShape() {
        const currentIndex = SHAPES.indexOf(shape.value)
        shape.value = SHAPES[(currentIndex + 1) % SHAPES.length]
        emit('change', shape.value)
    }
    

</script>


<template>
    
    <div @click="switchShape" class="cell">
        <Icon v-if="shape=='cross'"         icon="radix-icons:cross-1" width="10em" />
        <Icon v-else-if="shape=='circle'"   icon="radix-icons:circle" width="10em" />
    </div>

</template>


<style>

    .cell {
        border: dashed 5px rgb(0, 0, 0);
        min-width: 11em;
        min-height: 11em;
    }

</style>