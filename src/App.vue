<script setup>
import axios from "axios";
import { ref } from "vue";

const result = ref(null);
const sendPostRequest = () => {
  axios
    .post("https://reqres.in/api/users", {
      name: "Jane Doe " + Date.now(),
      age: 28,
    })
    .then((res) => {
      result.value = res;
    })
    .catch((err) => {
      result.value = err;
    });
};
</script>
<template>
  <div>
    <h1>Result:</h1>
    <p>
      {{ result }}
    </p>
    <button @click="sendPostRequest">Make request</button>
  </div>
</template>
<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
