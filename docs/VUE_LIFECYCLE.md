# Vue Lifecycle Hooks

This document explains the common lifecycle hooks in Vue.js and the order in which they are executed.

## Lifecycle Diagram Order

When a Vue component is created, it goes through a series of initialization steps. You can hook into these steps to run your own code.

### 1. Creation (Initialization)

- **`beforeCreate`**: Called immediately after the instance has been initialized. Data and events are not yet available.
- **`created`**: Called after the instance is finished processing. Data, computed properties, and methods are available, but the component has not been mounted to the DOM yet.

### 2. Mounting (DOM Insertion)

- **`beforeMount`**: Called right before the mounting begins. The template has been compiled, but not yet rendered to the screen.
- **`mounted`**: **(Used in this project)** Called after the component has been mounted to the DOM. This is the best place to perform side effects like **fetching data from an API** or interacting with the DOM.

### 3. Updates (Re-rendering)

- **`beforeUpdate`**: Called when data changes, before the DOM is patched.
- **`updated`**: Called after the DOM has been re-rendered due to a data change.

### 4. Destruction (Cleanup)

- **`beforeUnmount`** (Vue 3) / **`beforeDestroy`** (Vue 2): Called right before the component instance is destroyed. Good for cleaning up timers or global event listeners.
- **`unmounted`** (Vue 3) / **`destroyed`** (Vue 2): Called after the component instance has been destroyed.
