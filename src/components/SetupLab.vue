<script setup>
import { ref } from 'vue';

const message = ref('ready to start');

setTimeout(() => {
    message.value = "let's start!";
    console.log('message was updated successfully');
})

const domElement = document.getElementById('setup-box');
console.log('domElement is', domElement);
</script>

<template>
  <div class="lab-box">
    <h2>1. Setup Lab</h2>
    <p>Verifies behavior during component initialization (before DOM is available).</p>

    <div id="setup-box" class="data-box">
        {{ message }}
    </div>
  </div>
</template>

<style scoped>
.lab-box {
    background-color: #fcf3cf;
    padding: 15px;
    border-radius: 8px;
    border: 2px solid #f1c40f;
}
.data-box {
    margin-top: 10px;
    padding: 10px;
    background: white;
    border-radius: 4px;
    font-weight: bold;
}
</style>