<script setup>
import {
    onBeforeMount, onMounted,
    onBeforeUpdate, onUpdated,
    onBeforeUnmount, onUnmounted
} from 'vue';

defineProps(['count'])

console.log('[ChildComponent] setup was called');

onBeforeMount(() => {
    console.log('[ChildComponent] onBeforeMount was called');
})

onMounted(() => {
    console.log('[ChildComponent] onMounted was called');
})

onBeforeUpdate(() => {
    console.log('[ChildComponent] onBeforeUpdate was called');
})

onUpdated(() => {
    console.log('[ChildComponent] onUpdated was called');
})

onBeforeUnmount(() => {
    console.log('[ChildComponent] onBeforeUnmount was called');
})

onUnmounted(() => {
    console.log('[ChildComponent] onUnmounted was called');
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