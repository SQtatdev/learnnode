<script setup>
import L from 'leaflet'
import 'leaflet/dist/leaflet.css'
import { onMounted, watch, useId } from 'vue'

const props = defineProps({
  center: Array,
  homeCoords: Array,
  homePolygon: Array
})

let id = 'map-' + useId()
let map

onMounted(() => {
  map = L.map(id).setView(props.center, 16)

  L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution: '&copy; OpenStreetMap'
  }).addTo(map)

  if (props.homeCoords) {
    L.marker(props.homeCoords).addTo(map).bindPopup('Home')
  }

  if (props.homePolygon) {
    L.polygon(props.homePolygon, { color: 'blue' }).addTo(map)
  }
})

watch(() => props.center, (newCenter) => {
  if (map && newCenter) {
    map.setView(newCenter, map.getZoom())
  }
})
</script>

<template>
  <div :id="id"></div>
</template>

<style scoped>
div {
  height: 40vh;
}
</style>
