<script setup>
import { ref } from 'vue';
import MyInput from './components/MyInput.vue';

const value = ref();
</script>

<template>
  <MyInput v-model="value" />

  value: {{ value }}
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
