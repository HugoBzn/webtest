<template>
  <div class="px-6 py-6">
    <div class="block max-w-sm bg-gray-900 rounded-lg border border-purple-900 shadow-md hover:bg-gray-600">
      <img class="rounded-lg" :src="'http://localhost:1337' + image.url" />
      <h5 class="px-6 py-1 mb-2 text-2xl font-bold tracking-tight text-white">
        Username: <br />
        {{ user.firstName }} {{ user.lastName }}
      </h5>
      <p class="px-6 font-normal text-white">Email: {{ user.email }}</p>
      <p class="px-6 pb-2 font-normal text-white">Registered: {{ user.createdAt }}</p>
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
