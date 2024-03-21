<template>
  <button @click="page = 'home'">Home</button>
  <button @click="page = 'about'">About</button>

  <home v-if="page === 'home'" />
  <about v-else-if="page === 'about'" />
</template>

<script setup>
import Home from "./pages/Home.vue";
import About from "./pages/About.vue";
import { ref } from "vue";

const page = ref("home");
</script>

<style scoped></style>
