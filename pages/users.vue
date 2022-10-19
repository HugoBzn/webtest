<template>
  <div>
    <div class="grid lg:grid-cols-2 sm:grid-cols-1 gap-4 place-content-center">
      <Users v-for="user in users" :username="user" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const users = ref(['1', '2']);
</script>

<style scoped></style>
