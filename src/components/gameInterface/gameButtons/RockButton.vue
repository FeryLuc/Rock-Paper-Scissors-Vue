<script setup>
import { ref } from 'vue';
const name = ref('rock');
const emit = defineEmits(['rockMove']);
const rockMove = () => {
  emit('rockMove', name);
  console.log('Le bouton rock à été cliqué.');
};
</script>
<template>
  <button
    @click="rockMove"
    class="bg-red-600 text-6xl p-2 rounded duration-300 hover:opacity-75 hover:cursor-pointer"
  >
    &#x270A;
  </button>
</template>
