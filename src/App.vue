<script setup>
import { ref } from 'vue';

import LifecycleLogger from './components/LifecycleLogger.vue';
import SetupLab from './components/SetupLab.vue';
import MountedLab from './components/MountedLab.vue';
import UpdatedLab from './components/UpdatedLab.vue';
import UnmountedLab from './components/UnmountedLab.vue';

const currentLab = ref('logger');
</script>

<template>
  <div class="app-container">
    <h1>Vue Lifecycle Deconstruction</h1>
    <p>This is a simple app to demonstrate Vue lifecycle hooks.</p>

    <nav class="lab-nav">
      <button
        :class="{ active: currentLab === 'logger' }"
        @click="currentLab = 'logger'"
      >
        Execution Order
      </button>
      <button
        :class="{ active: currentLab === 'setup' }"
        @click="currentLab = 'setup'"
      >
        Setup
      </button>
      <button
        :class="{ active: currentLab === 'mounted' }"
        @click="currentLab = 'mounted'"
      >
        Mounted
      </button>
      <button
        :class="{ active: currentLab === 'updated' }"
        @click="currentLab = 'updated'"
      >
        Updated
      </button>
      <button
        :class="{ active: currentLab === 'unmounted' }"
        @click="currentLab = 'unmounted'" 
      >
        Unmounted
      </button>
    </nav>

    <hr />

    <main class="lab-content">
      <LifecycleLogger v-if="currentLab === 'logger'" />
      <SetupLab v-if="currentLab === 'setup'" />
      <MountedLab v-if="currentLab === 'mounted'" />
      <UpdatedLab v-if="currentLab === 'updated'" />
      <UnmountedLab v-if="currentLab === 'unmounted'" />
    </main>
  </div>

</template>

<style scoped>
.app-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  font-family: sans-serif;
}

header {
  margin-bottom: 20px;
}

.lab-nav {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  margin-bottom: 20px;
}

button {
  padding: 8px 16px;
  border: 1px solid #ccc;
  background-color: #f9f9f9;
  cursor: pointer;
  border-radius: 4px;
}

button.active {
  background-color: #42b883;
  color: white;
  border-color: #42b883;
}

.lab-content {
  padding: 20px;
  border: 2px dashed #ccc;
  border-radius: 8px;
  min-height: 200px;
}
</style>
