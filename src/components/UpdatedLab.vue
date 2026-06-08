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
    <div class="lab-box">
        <h2>Updated Lab</h2>
        <p>Verified that the component updates correctly when data changes</p>

        <button @click="addMessage" class="add-btn">
            Add Message
        </button>

        <div class="chat-box" ref="chatBoxRef">
            <div v-for="(msg, index) in messages" :key="index" class="message">
                {{ msg }}
            </div>
        </div>
    </div>
</template>

<style scoped>
.lab-box {
    background-color: #edf4f0;
    padding: 15px;
    border-radius: 8px;
    border: 2px solid #9b59b6;
}

.add-btn {
    margin-bottom: 10px;
    padding: 8px 16px;
    background-color: #9b59b6;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.add-btn:hover {
    background-color: #8e44ad;
}

.chat-box {
    height: 120px;
    overflow-y: auto;
    background-color: white;
    border: 1px solid #ccc;
    padding: 10px;
    border-radius: 4px;
}

.message {
    padding: 5px;
    border-bottom: 1px solid #eee;
}
</style>