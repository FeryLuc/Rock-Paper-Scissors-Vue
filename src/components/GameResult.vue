<script setup>
const props = defineProps({ data: Object });
console.log(props.data);
</script>
<template>
  <p class="text-xl font-semibold mb-4">{{ props.data.resultSentence }}</p>
  <p class="text-2xl font-semibold">
    Your score:
    <span class="text-blue-500">{{
      props.data.userScore ? props.data.userScore : 0
    }}</span>
    Computer score:
    <span class="text-red-500">{{
      props.data.computerScore ? props.data.computerScore : 0
    }}</span>
  </p>
</template>
