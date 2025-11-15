<script setup>
import RockButton from './gameButtons/RockButton.vue';
import PaperButton from './gameButtons/PaperButton.vue';
import ScissorsButton from './gameButtons/ScissorsButton.vue';
</script>
<template>
  <div>
    <h2 class="text-2xl font-semibold">Choose you move:</h2>
    <div id="btnContainer" class="mt-2 mb-4 flex justify-center gap-4">
      <rock-button />
      <paper-button />
      <scissors-button />
    </div>
  </div>
</template>
