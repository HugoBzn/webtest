<template>
  <div class="px-6 py-6">
    <div class="max-w-sm w-full lg:max-w-full lg:flex">
      <div class="pt-1 border border-gray-900 bg-gray-900 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden">
        <img class="rounded-lg" :src="'http://localhost:1337' + image.url" />
    </div>
      <div
        class="border border-gray-900 lg:border-l-0 lg:border-t lg:border-gray-900 bg-gray-900 rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal"
      >
        <div class="mb-8">
          <p class="text-sm text-gray-500 flex items-center">
            <svg class="fill-current text-gray-500 w-3 h-3 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
              <path
                d="M4 8V6a6 6 0 1 1 12 0v2h1a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2v-8c0-1.1.9-2 2-2h1zm5 6.73V17h2v-2.27a2 2 0 1 0-2 0zM7 6v2h6V6a3 3 0 0 0-6 0z"
              />
            </svg>
            Members only
          </p>
          <div class="text-gray-900 font-bold text-xl mb-2">
            <h5 class="px-6 py-1 mb-2 text-2xl font-bold tracking-tight text-white">
              Username: <br />
              {{ user.firstName }} {{ user.lastName }}
            </h5>
          </div>
          <p class="text-gray-700 text-base">
            <p class="px-6 font-normal text-white">Email: {{ user.email }}</p>
            <p class="px-6 pb-2 font-normal text-white">Registered: {{ user.createdAt }}</p>
          </p>
        </div>
        <div class="flex items-center">
          <img class="w-10 h-10 rounded-full mr-4" :src="'http://localhost:1337' + image.url"/>
          <div class="text-sm">
            <p class="text-gray-500 leading-none">{{ user.firstName }} {{ user.lastName }}</p>
            <p class="text-gray-500">{{ user.createdAt }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import axios from 'axios';
import { ref } from 'vue';

const props = defineProps({
  username: {
    type: String,
    required: true,
    default: 'No user',
  },
});

const user = ref('');
const image = ref('');

const id = props.username;

// Requesting data
(async function () {
  const res = await axios.get(`http://localhost:1337/api/bank-accounts/${id}/?populate=*`);
  user.value = res.data.data.attributes;
  image.value = res.data.data.attributes.image.data.attributes;
  user.value['createdAt'] = new Date(user.value['createdAt']).toDateString();
})();
</script>
