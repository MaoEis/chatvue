<script setup>
import { ref } from "vue";

let name = ref("User");
let messageText = ref("");

const emit = defineEmits(["sendMessage"]);

function doit() {
  if (messageText.value.trim() !== "") {
    const newMessage = {
      user: name.value,
      text: messageText.value,
    };

    console.log("Emitting message:", newMessage);
    emit("sendMessage", newMessage);
    messageText.value = "";
  }
}
</script>

<template>
  <div class="form">
    <div class="comment-section">
      <label for="name">{{ name }}:</label>
      <input
        v-model="messageText"
        type="text"
        placeholder="Type your message here..."
      />
      <button @click="doit">Send</button>
    </div>
  </div>
</template>

<style scoped>
.form {
  display: flex;
  gap: 10px;
  flex-direction: column;
  display: flex;
}
input {
  flex: 1;
  margin: 10px;
  width: 200px;
  font-size: 1rem;
  border: solid 1px grey;
  border-radius: 5px;
  padding: 3px;
}
</style>
