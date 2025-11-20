<script setup>
import GameTitle from './components/gameTitle.vue';
import GameResult from './components/gameResult.vue';
import GameInterface from './components/gameInterface/GameInterface.vue';
import { reactive } from 'vue';

const resultData = reactive({});
const storeData = (data) => {
  Object.assign(resultData, data);
  console.log(resultData);
};
</script>

<template>
  <section class="container mx-auto text-center mt-40">
    <GameTitle />
    <GameInterface @result="storeData" />
    <GameResult :data="resultData" />
  </section>
</template>

<style scoped></style>
