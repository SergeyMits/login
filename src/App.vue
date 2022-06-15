<script setup>
import { ref } from "vue";
import LogInVue from "./components/LogIn.vue";

const card = ref(false);
const card2 = ref(false);
</script>

<template>
  <div
    class="p-4 min-h-screen w-full bg-base-300 flex items-center justify-center"
  >
    <LogInVue />
  </div>
</template>
