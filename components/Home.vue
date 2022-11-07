<template>
  <div class="lg:columns-3 md:columns-3 my-5 ml-10">
    <div class="max-w-sm bg-gray-800 rounded-lg border border-gray-700 shadow-md">
      <div class="w-full h-full">
        <img class="rounded-t-lg" src="@/assets/images/h.png" alt="" />
      </div>
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-white">{{ $t('MethodPost') }}</h5>
        <p class="mb-3 font-normal text-gray-400">{{ $t('DescPost') }}</p>
        <div class="center">
          <NuxtLink
            to="/post"
            class="transition duration-300 ease-in-out centertext-white bg-gradient-to-br from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
          >
            Go to page!
          </NuxtLink>
          <br />
        </div>
      </div>
    </div>
    <br />

    <div class="max-w-sm bg-gray-800 rounded-lg border border-gray-700 shadow-md">
      <img class="rounded-t-lg" src="@/assets/images/h.png" alt="" />
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-white">Method Post with image</h5>
        <p class="mb-3 font-normal text-gray-400">The next page is a form with image.</p>
        <div class="center">
          <NuxtLink
            to="/postImage"
            class="transition duration-300 ease-in-out centertext-white bg-gradient-to-br from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
          >
            Go to page!
          </NuxtLink>
          <br />
        </div>
      </div>
    </div>
    <br />

    <div class="max-w-sm bg-gray-800 rounded-lg border border-gray-700 shadow-md">
      <img class="rounded-t-lg" src="@/assets/images/h.png" alt="" />
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-white">Page users</h5>
        <p class="mb-3 font-normal text-gray-400">Page wehere you can see all the users without picture.</p>
        <div class="center">
          <NuxtLink
            to="/info"
            class="transition duration-300 ease-in-out centertext-white bg-gradient-to-br from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
          >
            Go to page!
          </NuxtLink>
          <br />
        </div>
      </div>
    </div>
    <br />

    <div class="max-w-sm bg-gray-800 rounded-lg border border-gray-700 shadow-md">
      <div class="w-full h-full">
        <iframe
          class="w-full"
          src="https://www.youtube.com/embed/sFrNsSnk8GM"
          allowfullscreen
          style="height: 215px"
        ></iframe>
      </div>
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-white">Map Page</h5>
        <p class="mb-3 font-normal text-gray-400">Mapa</p>
        <div class="center">
          <NuxtLink
            to="/mapa"
            class="transition duration-300 ease-in-out centertext-white bg-gradient-to-br from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
          >
            Go to page!
          </NuxtLink>
          <br />
        </div>
      </div>
    </div>
    <br />

    <div class="max-w-sm bg-gray-800 rounded-lg border border-gray-700 shadow-md">
      <div class="w-full h-full">
        <img class="rounded-t-lg" src="@/assets/images/h.png" alt="" />
      </div>
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-white">Page users with Images</h5>
        <p class="mb-3 font-normal text-gray-400">Page where you can see all the registered users.</p>
        <div class="center">
          <NuxtLink
            to="/users"
            class="transition duration-300 ease-in-out centertext-white bg-gradient-to-br from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
          >
            Go to page!
          </NuxtLink>
          <br />
        </div>
      </div>
    </div>
    <br />

    <div class="max-w-sm bg-gray-800 rounded-lg border border-gray-700 shadow-md">
      <img class="rounded-t-lg" src="@/assets/images/logoApex.jpg" alt="" />
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-white">Page Apex Legends</h5>
        <p class="mb-3 font-normal text-gray-400">
          My profile in Apex Legends eith all my data with my favorite legend.
        </p>
        <div class="center">
          <NuxtLink
            to="/profile"
            class="transition duration-300 ease-in-out centertext-white bg-gradient-to-br from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
          >
            Go to page!
          </NuxtLink>
          <br />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style></style>
