<script setup>
import { ref } from "vue";
import ChatMessages from "./ChatMessages.vue";
import ChatForm from "./ChatForm.vue";

const messages = ref([]);

function addMessage(newMessage) {
  messages.value.push(newMessage);
}
</script>

<template>
  <ChatMessages :messages="messages" />
  <ChatForm @sendMessage="addMessage" />
</template>

<style scoped></style>
