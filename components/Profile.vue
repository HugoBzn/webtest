<template>
  <div class="px-6 py-6">
    <div class="grid lg:grid-cols-12 sm:grid-cols-1 place-content-center mb-4">
      <p class="col-span-12 text-xl text-center">Username: {{ user.name }} ⛩️ Level: 500 + {{ user.level }}</p>
    </div>
    <div class="grid lg:grid-cols-12 sm:grid-cols-1 gap-4 place-content-center">
      <!-- First Card Valk -->
      <div class="col-span-4 text-white place-items-center">
        <div class="max-w-sm rounded overflow-hidden shadow-lg border border-purple-800">
          <div class="mt-6 font-bold text-xl mb-2 flex items-center justify-center">
            <h1>Valkyrie</h1>
          </div>
          <img class="w-full" :src="ValkImage.icon" alt="Icon" />
          <div class="px-6 py-4">
            <p class="text-white font-bold" v-for="{ name, value } in StatsValk" :key="name">{{ name }}: {{ value }}</p>
          </div>
        </div>
      </div>
      <!-- Second Card -->
      <div class="col-span-4 text-white place-items-center">
        <div class="max-w-sm rounded overflow-hidden shadow-lg border border-purple-800">
          <div class="mt-6 font-bold text-xl mb-2 flex items-center justify-center">
            <h1>Pathfinder</h1>
          </div>
          <img class="w-full" :src="PathImage.icon" alt="Icon" />
          <div class="px-6 py-4">
            <p class="text-white font-bold" v-for="{ name, value } in StatsPath" :key="name">{{ name }}: {{ value }}</p>
          </div>
        </div>
      </div>
      <!-- Third Card -->
      <div class="col-span-4 text-white place-items-center">
        <div class="max-w-sm rounded overflow-hidden shadow-lg border border-purple-800">
          <div class="mt-6 font-bold text-xl mb-2 flex items-center justify-center">
            <h1>Horizon</h1>
          </div>
          <img class="w-full" :src="HorizonImage.icon" alt="Icon" />
          <div class="px-6 py-4">
            <p class="text-white font-bold" v-for="{ name, value } in StatsHorizon" :key="name">
              {{ name }}: {{ value }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';

const user = ref('');

// Valkyrie Data
const StatsValk = ref([]);
const ValkImage = ref('');

// Pathfinder Data
const StatsPath = ref([]);
const PathImage = ref('');

// Pathfinder Data
const StatsHorizon = ref([]);
const HorizonImage = ref('');

// Requesting data
(async function () {
  const res = await axios.get(
    'https://api.mozambiquehe.re/bridge?auth=af654fd080951f489178e9bd2f910580&player=Vitryolz&platform=X1'
  );
  // My Data
  user.value = res.data.global;

  // Data Valk
  ValkImage.value = res.data.legends.all.Valkyrie.ImgAssets;
  StatsValk.value = res.data.legends.all.Valkyrie.data;

  // Data Pathfinder
  PathImage.value = res.data.legends.all.Pathfinder.ImgAssets;
  StatsPath.value = res.data.legends.all.Pathfinder.data;

  // Data Horizon
  HorizonImage.value = res.data.legends.all.Horizon.ImgAssets;
  StatsHorizon.value = res.data.legends.all.Horizon.data;
})();
</script>
