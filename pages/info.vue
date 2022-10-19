<template>
  <div class="grid lg:grid-cols-3 sm:grid-cols-1 gap-4 place-content-center">
    <Info v-for="user in users" :username="user" />
  </div>
</template>

<script setup>
import { ref } from 'vue';

const users = ref(['1', '2', '7', '8', '9']);
</script>

<style scoped></style>
