<script setup>
import { ref, onMounted } from 'vue';

const inputRef = ref(null);

console.log('[MountedLab] setup was called');
console.log('[MountedLab] inputRef in setup is:', inputRef.value);

onMounted(() => {
    console.log('[MountedLab] onMounted was executed');
    console.log('[MountedLab] inputRef in onMounted is:', inputRef.value);

    if (inputRef.value) {
        inputRef.value.focus()
        console.log('[MountedLab] Input focused automatically');
    }
})
</script>

<template>
  <div class="lab-box">
    <h2>2. Mounted Lab</h2>
    <p>Verifies processes that can only be performed "after" the DOM (HTML) has been completely generated.</p>

    <div class="input-area">
      <label for="auto-focus-input">Input field that is automatically focused immediately after mounting:</label>
      <input 
        id="auto-focus-input"
        type="text" 
        ref="inputRef" 
        placeholder="Type something here..." 
      />
    </div>
  </div>
</template>

<style scoped>
.lab-box {
  background-color: #d4efdf; /* Greenish background */
  padding: 15px;
  border-radius: 8px;
  border: 2px solid #27ae60;
}
.input-area {
  margin-top: 15px;
  display: flex;
  flex-direction: column;
  gap: 8px;
}
input {
  padding: 8px;
  border-radius: 4px;
  border: 1px solid #7dcea0;
  width: 100%;
  max-width: 300px;
}
input:focus {
  outline: none;
  border-color: #27ae60;
  box-shadow: 0 0 5px rgba(39, 174, 96, 0.5);
}
</style>