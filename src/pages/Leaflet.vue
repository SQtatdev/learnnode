<script setup>
import { ref, nextTick } from 'vue'
import LeafletMap from '../comp/LeafletMap.vue'

const cords = ref([59.415404, 24.646672])
const homeCoords = [59.417, 24.645]
const homePolygon = [
  [59.4172, 24.6448],
  [59.4172, 24.6452],
  [59.4168, 24.6452],
  [59.4168, 24.6448]
]

function goToHome() {
  cords.value = null
  nextTick(() => {
    cords.value = [...homeCoords]  // копия массива
  })
}
</script>

<template>
  <button @click="goToHome">Go home</button>
  <LeafletMap
    :center="cords"
    :home-coords="homeCoords"
    :home-polygon="homePolygon"
  />
</template>
