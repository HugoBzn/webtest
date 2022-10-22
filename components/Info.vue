<template>
  <div class="px-6 py-6">
    <div class="max-w-sm rounded overflow-hidden shadow-lg border border-purple-900 bg-gray-900">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">{{ user.firstName || "No user"}} {{ user.lastName }} </div>
        <p class="text-white text-base">Company: {{ user.company }}</p>
        <p class="text-white text-base">Phone Number: {{ user.phoneNumber }}</p>
        <p class="text-white text-base">Email: {{ user.email }}</p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">
          #strapi
        </span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">
          #infos
        </span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">
          #winteriscoming
        </span>
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

const id = props.username;

// Requesting data
(async function () {
  const res = await axios.get(`http://localhost:1337/api/infos/${id}`);
  user.value = res.data.data.attributes;
  user.value['createdAt'] = new Date(user.value['createdAt']).toDateString();
})();
</script>

<style scoped></style>
