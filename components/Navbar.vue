<template>
  <div class="bg-gradient-to-r from-sky-900 to-purple-900">
    <nav class="container py-2 mx-auto md:flex md:justify-between md:items-center">
      <div class="flex items-center justify-between">
        <NuxtLink to="/" class="text-xl font-bold text-gray-100 md:text-2xl hover:text-indigo-400">
          <img src="@/assets/images/palm.gif" class="rounded-full scale-100" width="70px">
        </NuxtLink>
        <!-- Mobile menu button -->
        <div @click="toggleNav" class="flex md:hidden">
          <button type="button" class="text-gray-100 hover:text-gray-400 focus:outline-none focus:text-gray-400">
            <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
              <path fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z">
              </path>
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
      <ul :class="showMenu ? 'flex' : 'hidden'"
        class="flex-col mt-8 space-y-4 md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0">
        <button
          class="mt-2 relative inline-flex items-center justify-center p-0.5 mb-2 mr-2 overflow-hidden text-sm font-medium text-white rounded-lg group bg-gradient-to-br from-purple-600 to-blue-500 group-hover:from-purple-600 group-hover:to-blue-500 hover:text-white dark:text-white focus:ring-4 focus:outline-none">
          <span
            class="relative px-5 py-2.5 transition-all ease-in bg-black duration-75 rounded-md group-hover:bg-opacity-0">
            <NuxtLink to="/">Home</NuxtLink>
          </span>
        </button>
        <button
          class="relative inline-flex items-center justify-center p-0.5 mb-2 mr-2 overflow-hidden text-sm font-medium text-white rounded-lg group bg-gradient-to-br from-purple-500 to-pink-500 group-hover:from-purple-500 group-hover:to-pink-500 hover:text-white dark:text-white focus:ring-4 focus:outline-none focus:ring-purple-600">
          <span
            class="relative px-5 py-2.5 transition-all ease-in duration-75 bg-black rounded-md group-hover:bg-opacity-0">
            <NuxtLink to="/">Home</NuxtLink>
          </span>
        </button>
        <button
          class="relative inline-flex items-center justify-center p-0.5 mb-2 mr-2 overflow-hidden text-sm font-medium text-white rounded-lg group bg-gradient-to-br from-pink-500 to-orange-400 group-hover:from-pink-500 group-hover:to-orange-400 hover:text-white dark:text-white focus:ring-4 focus:outline-none focus:ring-pink-600">
          <span
            class="relative px-5 py-2.5 transition-all ease-in duration-75 bg-black rounded-md group-hover:bg-opacity-0">
            <NuxtLink to="/">Home</NuxtLink>
          </span>
        </button>
      </ul>
    </nav>
  </div>
</template>

<script setup>
import { ref } from "vue";

const showMenu = ref(false);
const toggleNav = () => (showMenu.value = !showMenu.value);

</script>

<style scoped>

</style>
