<script setup>
import {
    onBeforeMount, onMounted,
    onBeforeUpdate, onUpdated,
    onBeforeUnmount, onUnmounted
} from 'vue';

defineProps(['count'])

console.log('setup was called');

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
    <div class="child-box">
        <h3>Child Component</h3>
        <p>Here's the count which is received from the parent: {{ count }}</p>
    </div>
</template>

<style>
.child-box {
    border: 2px solid #3498db;
    padding: 10px;
    border-radius: 8px;
    background-color: #ebf5fb;
    margin-top: 15px;
}
</style>