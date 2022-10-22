<template>
  <div>
    <div class="grid lg:grid-cols-2 sm:grid-cols-1 gap-4 place-content-center">
      <Users v-for="user in 6" :username="user" />
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped></style>
