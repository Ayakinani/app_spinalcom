<template>
  <div>
    <h1 class="building-name"><span>Pourcentage d'occupation du bâtiment :</span> Usine</h1>
    <div v-for="floor in building.floors" :key="floor.name">
      <Floor :floor-data="floor" />
    </div>
  </div>
</template>

<script setup>
import { buildingData as building } from '../Data.js';
import Floor from './Floor.vue';
</script>


<style scoped>
.building-name span {
color: #211d6b
}

.building-name {
  /* Style for the building name */
  color: #fd8700;
}
</style>