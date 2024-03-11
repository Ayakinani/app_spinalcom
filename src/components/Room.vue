<template>
  <div class="room" :class="{ 'occupied': roomData.occupied, 'not-occupied': !roomData.occupied, 'unknown': roomData.occupied === undefined }">
    <span class="room-name">{{ roomData.name }}</span>
    <span v-if="roomData.occupied !== undefined" class="occupation-status" :class="{ 'status-occupied': roomData.occupied, 'status-not-occupied': !roomData.occupied }">
      {{ roomData.occupied ? 'Occupied' : 'Not Occupied' }}
    </span>
    <span v-else class="occupation-status status-unknown">Status unknown</span>
  </div>
</template>


<script setup>
// defineProps is a compiler macro, so no import is necessary
const props = defineProps({
  roomData: {
    type: Object,
    required: true
  }
});
</script>
