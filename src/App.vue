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
        @click="currentLab = 'updated'" 
      >
        Unmounted
      </button>
    </nav>

    <hr />

    <main>
      <LifecycleLogger />
      <SetupLab />
      <MountedLab />
      <UpdatedLab />
      <UnmountedLab />
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


</style>
