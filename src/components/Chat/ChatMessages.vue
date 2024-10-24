<script setup>
import { defineProps } from "vue";

const props = defineProps({
  messages: {
    type: Array,
    required: true,
  },
});
</script>

<template>
  <div class="comments">
    <ul>
      <li
        v-for="(message, index) in props.messages.slice().reverse()"
        :key="index"
      >
        <strong
          ><p>{{ message.user }}</p></strong
        >

        <p>{{ message.text }}</p>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.comments {
  margin-right: 50px;
  padding: 5px;
  border: 1px solid #000000;
  border-radius: 10px;
  height: 250px;
  width: 40vw;
  overflow-y: scroll;
}
.comments ul {
  list-style-type: none;
  padding: 5px;
}
.comments li {
  margin-bottom: 5px;
  padding-left: 5px;
  border: 1px solid #ccc;
  border-radius: 5px;
  display: flex;
  flex-direction: row;
}

.comments li p {
  margin: 10px 5px;
}
</style>
