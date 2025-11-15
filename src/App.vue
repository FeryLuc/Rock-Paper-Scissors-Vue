<script setup>
import GameTitle from './components/gameTitle.vue';
import GameResult from './components/gameResult.vue';
import GameInterface from './components/gameInterface/GameInterface.vue';
</script>

<template>
  <section class="container mx-auto text-center mt-40">
    <GameTitle />
    <GameInterface />
    <GameResult />
  </section>
</template>

<style scoped></style>
