<script setup>
import {
    ref,
    onBeforeMount, onMounted,
    onBeforeUpdate, onUpdated,
    onBeforeUnmount, onUnmounted
} from 'vue';
import ChildComponent from './ChildComponent.vue';

const parentCount = ref(0);

onBeforeMount(() => {
    console.log('onBeforeMount was called');
})

onMounted(() => {
    console.log('onMounted was called');
})

onBeforeUpdate(() => {
    console.log('onBeforeUpdate was called');
})

onUpdated(() => {
    console.log('onUpdated was called');
})

onBeforeUnmount(() => {
    console.log('onBeforeUnmount was called');
})

onUnmounted(() => {
    console.log('onUnmounted was called');
})
</script>

<template>
    <div>
        <h2>Lifecycle Logger</h2>
        <p>Check the log with using developer tools</p>
        
        <button @click="parentCount++">
            {{  parentCount  }}
        </button>

        <ChildComponent :count="parentCount" />
    </div>
</template>

<style>

</style>