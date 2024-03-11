<template>
  <div id="app">
    <Building :building-data="geographicContextSpace" />
  </div>
</template>

<script setup>
import { geographicContextSpace } from './data/geographicContextSpace.js';
import Building from './components/Building.vue';
</script>

<style>

.floor {
  cursor: pointer;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 8px;
  margin-bottom: 1rem;
  color: #211d6b;
  background-color: #cccfec;
}


.building, .floor {
  margin-bottom: 1rem;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 8px;
}

.room {
  padding: 0.5rem;
  margin: 0.5rem 0;
  border: 1px solid #eee;
  border-radius: 4px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.not-occupied {
  background-color: #cca2a2; /* Light green background for occupied rooms */
  color: #880101; /* Green text color for occupied rooms */
}


.occupied {
  background-color: #b0e396; /* Light red background for not occupied rooms */
  color: darkgreen;
}

.unknown {
  background-color: #e0e0e0; /* Grey background for rooms with undefined status */
  color: #181818;
}

.room-name {
  font-weight: bold;
}

.occupation-status {
  padding: 2px 5px;
  border-radius: 6px;
  color: #000000;
  font-size: 0.8rem;
}




body {
  font-family: 'Roboto', sans-serif;
}

</style>