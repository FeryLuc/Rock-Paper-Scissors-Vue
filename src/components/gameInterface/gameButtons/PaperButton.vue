<script setup>
import { ref } from 'vue';
const name = ref('paper');
const emit = defineEmits(['paperMove']);
const paperMove = () => {
  emit('paperMove', name);
  console.log('Le bouton paper à été cliqué.');
};
</script>

<template>
  <button
    class="bg-blue-600 text-6xl p-2 rounded duration-300 hover:opacity-75 hover:cursor-pointer"
    @click="paperMove"
  >
    &#x270B;
  </button>
</template>
