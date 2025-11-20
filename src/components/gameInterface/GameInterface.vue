<script setup>
import RockButton from './gameButtons/RockButton.vue';
import PaperButton from './gameButtons/PaperButton.vue';
import ScissorsButton from './gameButtons/ScissorsButton.vue';

import { ref, computed } from 'vue';
const userChoice = ref(null);
const computerChoice = ref(null);
const randomNb = ref(0);
const userScore = ref(0);
const computerScore = ref(0);
const resultSentence = ref('');

const computerMove = computed(() => {
  switch (randomNb.value) {
    case 1:
      computerChoice.value = 'rock';
      break;
    case 2:
      computerChoice.value = 'paper';
      break;
    case 3:
      computerChoice.value = 'scissors';
      break;
    default:
      break;
  }
  return computerChoice.value;
});
const playGame = (data) => {
  userChoice.value = data.value;
  randomNb.value = Math.floor(Math.random() * 3 + 1);
  computerChoice.value = computerMove.value;

  if (userChoice.value === computerChoice.value) {
    resultSentence.value = `It's a tie ! a ${userChoice.value} is a ${computerChoice.value}`;
  } else if (
    (userChoice.value === 'rock' && computerChoice.value === 'scissors') ||
    (userChoice.value === 'paper' && computerChoice.value === 'rock') ||
    (userChoice.value === 'scissors' && computerChoice.value === 'paper')
  ) {
    resultSentence.value = `You win ! ${userChoice.value} beats ${computerChoice.value}`;
    userScore.value++;
  } else {
    resultSentence.value = `You lose ! ${userChoice.value} is beaten by ${computerChoice.value}`;
    computerScore.value++;
  }

  console.log(randomNb.value, userChoice.value, computerChoice.value);
};

const emit = defineEmits(['result']);
const sendResult = () => {
  emit('result', {
    userScore: userScore.value,
    computerScore: computerScore.value,
    resultSentence: resultSentence.value,
  });
};
</script>
<template>
  <div>
    <h2 class="text-2xl font-semibold">Choose your move:</h2>
    <div class="mt-2 mb-4 flex justify-center gap-4">
      <rock-button @rock-move="playGame" @click="sendResult" />
      <paper-button @paper-move="playGame" @click="sendResult" />
      <scissors-button @scissors-move="playGame" @click="sendResult" />
    </div>
  </div>
</template>
