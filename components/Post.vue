<template>
  <div class="px-6 py-6">
    <form @submit.prevent="postData" id="form" method="post">
      <div class="grid gap-6 mb-6 md:grid-cols-2">
        <div>
          <label for="first_name" class="block mb-2 text-sm font-medium text-white">First name</label>
          <input
            type="text"
            id="first_name"
            class="bg-gray-800 border border-gray-300 text-white text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
            placeholder="John"
            required=""
            v-model="firstName"
          />
        </div>
        <div>
          <label for="last_name" class="block mb-2 text-sm font-medium text-white"> Last name </label>
          <input
            type="text"
            id="last_name"
            class="bg-gray-800 border border-gray-300 text-white text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
            placeholder="Doe"
            required=""
            v-model="lastName"
          />
        </div>
        <div>
          <label for="company" class="block mb-2 text-sm font-medium text-white">Company</label>
          <input
            type="text"
            id="company"
            class="bg-gray-800 border border-gray-300 text-white text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
            placeholder="Flowbite"
            required=""
            v-model="company"
          />
        </div>
        <div>
          <label for="phone" class="block mb-2 text-sm font-medium text-white"> Phone number </label>
          <input
            type="text"
            id="phone"
            class="bg-gray-800 border border-gray-300 text-white text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
            placeholder="5534121243"
            required
            v-model="phoneNumber"
          />
        </div>
      </div>
      <label for="email" class="block mb-2 text-sm font-medium text-white"> Your Email </label>
      <div class="relative mb-6">
        <div class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none">
          <svg
            aria-hidden="true"
            class="w-5 h-5 text-gray-500 dark:text-gray-400"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"></path>
            <path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"></path>
          </svg>
        </div>
        <input
          type="email"
          id="email"
          class="bg-gray-800 border border-gray-300 text-white text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
          placeholder="name@flowbite.com"
          required
          v-model="email"
        />
      </div>
      <div class="mb-6">
        <label for="password" class="block mb-2 text-sm font-medium text-white">Password</label>
        <input
          type="password"
          id="password"
          class="bg-gray-800 border border-gray-300 text-white text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
          placeholder="•••••••••"
          required=""
          v-model="password"
        />
      </div>
      <div class="mb-6">
        <label for="confirm_password" class="block mb-2 text-sm font-medium text-white">Confirm password</label>
        <input
          type="password"
          id="confirm_password"
          class="bg-gray-800 border border-gray-300 text-white text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
          placeholder="•••••••••"
          required=""
        />
      </div>
      <button
        type="submit"
        class="text-white bg-gradient-to-r from-purple-500 via-purple-600 to-purple-700 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-purple-300 shadow-lg shadow-purple-500/50 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
      >
        Submit
      </button>
    </form>
  </div>
</template>

<script>
export default {
  methods: {
    async postData() {
      const response = await fetch('http://localhost:1337/api/infos', {
        method: 'POST',
        headers: {
          'Content-type': 'application/json; charset=UTF-8',
        },
        body: JSON.stringify({
          data: {
            firstName: this.firstName,
            lastName: this.lastName,
            company: this.company,
            phoneNumber: this.phoneNumber,
            email: this.email,
            password: this.password,
          },
        }),
      });
      const content = await response.json();
      console.log(content);
    },
  },
  data() {
    return {
      firstName: '',
      lastName: '',
      company: '',
      phoneNumber: '',
      email: '',
      password: '',
    };
  },
};
</script>
