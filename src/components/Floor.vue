<template>
  <div class="floor" @click="toggle">
    <h2>{{ floorData.name }} : {{ occupationPercentage }}%</h2>
    <transition name="fade">
      <div v-if="showDetails">
        <div v-for="room in floorData.rooms" :key="room.name">
          <Room :room-data="room" />
        </div>
      </div>
    </transition>
  </div>
</template>

<script setup>
import {ref, computed} from 'vue';
import Room from './Room.vue';

const props = defineProps({
  floorData: Object
});
const showDetails = ref(false);

const occupationPercentage = computed(() => {
  const occupiedRooms = props.floorData.rooms.filter(room => room.occupied).length;
  const totalRooms = props.floorData.rooms.length;
  return totalRooms > 0 ? ((occupiedRooms / totalRooms) * 100).toFixed(2) : 0;
});

const toggle = () => {
  showDetails.value = !showDetails.value;
};
</script>
