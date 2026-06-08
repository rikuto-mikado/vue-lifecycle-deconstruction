<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const timer = ref(0);
let timerId = null;

onMounted(() => {
    console.log('[UnmountedLab] component mounted, starting timer');

    timerId = setInterval(() => {
        timer.value++;
        console.log(`[UnmountedLab] Time: ${timer.value}`);
    }, 1000);
})

onUnmounted(() => {
    clearInterval(timerId);
    console.log('[UnmountedLab] component unmounted, timer stopped');
})
</script>

<template>
    <div class="lab-box">
        <h2>Unmounted Lab</h2>
        <p>Verified that the component cleans up its resources when unmounted</p>
        <div class="counter">
            Timer: {{ timer }}
        </div>
        <p style="font-size: .8em; color: #666;">
            When you switch to another lab, this component will be unmounted and the timer will stop,
            which you can verify by checking the console logs to see whether the timer is still running or not
        </p>
    </div>
</template>

<style scoped>
.lab-box {
    background-color: #f5b7b1;
    padding: 15px;
    border-radius: 8px;
    border: 2px solid #c0392b;
}
.timer {
    font-size: 1.5em;
    font-weight: bold;
    text-align: center;
    margin: 10px 0;
}
</style>