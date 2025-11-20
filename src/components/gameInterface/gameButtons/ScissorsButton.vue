<script setup>
import { ref } from 'vue';
const name = ref('scissors');
const emit = defineEmits(['scissorsMove']);
const scissorsMove = () => {
  emit('scissorsMove', name);
  console.log('Le bouton scissors à été cliqué.');
};
</script>
<template>
  <button
    @click="scissorsMove"
    class="bg-green-600 text-6xl p-2 rounded duration-300 hover:opacity-75 hover:cursor-pointer"
  >
    &#x270C;
  </button>
</template>
