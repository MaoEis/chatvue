<script setup>
import { ref } from "vue";
import { defineEmits } from "vue";

const message = ref("");
const emit = defineEmits(["sendMessage"]);

function doit() {
  if (message.value.trim() !== "") {
    emit("sendMessage", { user: "Mai", text: message.value });
    message.value = "";
  }
}
</script>

<template>
  <div class="form">
    <input v-model="message" type="text" placeholder="Type your message..." />
    <button @click.prevent="doit">Send</button>
  </div>
</template>

<style scoped></style>
