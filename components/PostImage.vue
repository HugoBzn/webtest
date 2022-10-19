<template>
  <div class="px-6 py-6">
    <form @submit.prevent="postData" id="form" method="post">
      <div class="grid md:grid-cols-2 md:gap-6">
        <div class="relative z-0 mb-6 w-full group">
          <input
            type="text"
            name="first_name"
            id="floating_first_name"
            class="block py-2.5 px-0 w-full text-sm text-white bg-transparent border-0 border-b-2 border-gray-300 appearance-none focus:outline-none focus:ring-0 focus:border-blue-600 peer"
            placeholder=" "
            required
            v-model="firstName"
          />
          <label
            for="floating_first_name"
            class="peer-focus:font-medium absolute text-sm text-gray-300 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6"
          >
            First name
          </label>
        </div>
        <div class="relative z-0 mb-6 w-full group">
          <input
            type="text"
            name="last_name"
            id="floating_last_name"
            class="block py-2.5 px-0 w-full text-sm text-white bg-transparent border-0 border-b-2 border-gray-300 appearance-none focus:outline-none focus:ring-0 focus:border-blue-600 peer"
            placeholder=" "
            required
            v-model="lastName"
          />
          <label
            for="floating_last_name"
            class="peer-focus:font-medium absolute text-sm text-gray-300 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6"
          >
            Last name
          </label>
        </div>
      </div>
      <div class="relative z-0 mb-6 w-full group">
        <input
          type="email"
          name="email"
          id="floating_email"
          class="block py-2.5 px-0 w-full text-sm text-white bg-transparent border-0 border-b-2 border-gray-300 appearance-none focus:outline-none focus:ring-0 focus:border-blue-600 peer"
          placeholder=" "
          required
          v-model="email"
        />
        <label
          for="floating_email"
          class="peer-focus:font-medium absolute text-sm text-gray-300 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6"
        >
          Email address
        </label>
      </div>
      <div class="relative z-0 mb-6 w-full group">
        <input
          type="password"
          name="password"
          id="floating_password"
          class="block py-2.5 px-0 w-full text-sm text-white bg-transparent border-0 border-b-2 border-gray-300 appearance-none focus:outline-none focus:ring-0 focus:border-blue-600 peer"
          placeholder=" "
          required
          v-model="password"
        />
        <label
          for="floating_password"
          class="peer-focus:font-medium absolute text-sm text-gray-300 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6"
        >
          Password
        </label>
      </div>
      <div class="relative z-0 mb-6 w-full group">
        <input
          type="password"
          name="password"
          id="floating_repeat_password"
          class="block py-2.5 px-0 w-full text-sm text-white bg-transparent border-0 border-b-2 border-gray-300 appearance-none focus:outline-none focus:ring-0 focus:border-blue-600 peer"
          placeholder=" "
          required
          v-model="confirmPassword"
        />
        <label
          for="floating_repeat_password"
          class="peer-focus:font-medium absolute text-sm text-gray-300 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-blue-600 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6"
        >
          Confirm password
        </label>
      </div>
      <label for="countries" class="block mb-2 text-sm font-medium text-gray-300"> Select your image </label>
      <select
        id="countries"
        class="bg-transparent mb-3 border border-gray-300 text-white text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
        v-model="image"
      >
        <option value="1" class="bg-purple-900">1. Kairi</option>
        <option value="2" class="bg-purple-900">2. Kiriko</option>
        <option value="3" class="bg-purple-900">3. Hugo</option>
        <option value="4" class="bg-purple-900">4. Draken</option>
      </select>
      <button
        type="submit"
        class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center"
      >
        Submit
      </button>
    </form>
  </div>
</template>

<script setup>
import axios from 'axios';
import { ref } from 'vue';

// Data
const firstName = ref('');
const lastName = ref('');
const email = ref('');
const password = ref('');
const image = ref();
const confirmPassword = ref('');

// Method POST
const postData = () => {
  axios
    .post('http://localhost:1337/api/bank-accounts', {
      data: {
        firstName: firstName.value,
        lastName: lastName.value,
        email: email.value,
        password: password.value,
        image: image.value,
      },
    })
    .then((res) => {
      console.log(res);
    });

  // Method clean form
  clearForm();
};

// Method clearForm
const clearForm = () => {
  firstName.value = '';
  lastName.value = '';
  email.value = '';
  password.value = '';
  confirmPassword.value = '';
  image.value = '';
};
</script>
