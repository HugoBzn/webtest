<template>
  <div class="px-6 py-6">
    <h1>{{ $t('welcome') }}</h1>
    <div id="mapContainer">
      <!-- <button @click="setupLeafletMap()">ASD</button> -->
    </div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';

const center = [24.0346902, -104.6817882];

const setupLeafletMap = () => {
  const mapDiv = L.map('mapContainer').setView(center, 13);

  L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution:
      'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="http://cloudmade.com">CloudMade</a>',
    maxZoom: 18,
  }).addTo(mapDiv);

  L.control.scale().addTo(mapDiv);
  L.marker([24.0346902, -104.6817882], { draggable: true }).addTo(mapDiv);

  L.marker([24.0346902, -104.6817882]).addTo(mapDiv).bindPopup('Tengo hambre 🍔.').closePopup();
};

onMounted(() => {
  setupLeafletMap();
});
</script>
