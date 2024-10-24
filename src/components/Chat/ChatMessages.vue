<script setup>
import { onMounted, reactive, defineProps } from "vue";

const messages = reactive([]);
const props = defineProps({
  messages: Array,
});

onMounted(() => {
  fetch("https://les3mongodb-y1hu.onrender.com/api/v1/messages")
    .then((response) => response.json())
    .then((data) => {
      messages.push(...data.data.messages);
    });
});
</script>

<template>
  <h1>Chat message</h1>
  <ul>
    <li v-for="message in [...messages, ...props.messages]" :key="message.id">
      <strong>{{ message.user }}</strong
      >: {{ message.text }}
    </li>
  </ul>
</template>

<style scoped></style>
