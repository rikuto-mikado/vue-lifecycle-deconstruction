<script setup>
import { ref, onUpdated } from 'vue';

const messages = ref(['Initial message']);
const chatBoxRef = ref(null);

const addMessage = () => {
    messages.value.push(`New message ${messages.value.length + 1}`)
    console.log('Added a new data [UpdatedLab], which isnt updated in the DOM yet');
}

onUpdated(() => {
    console.log('[UpdatedLab] onUpdated');

    if (chatBoxRef.value) {
        chatBoxRef.value.scrollTop = chatBoxRef.value.scrollHeight;
        console.log('[UpdatedLab] chat box scrooled to the bottom')
    }
})
</script>

<template>
    
</template>