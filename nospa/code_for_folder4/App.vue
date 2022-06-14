<template>
  <h1 class="mt-10 text-6xl text-center">Ninja Reaction Timer</h1>
  <button
    @click="waitASec()"
    class="block px-3 py-2 mx-auto text-white bg-green-700 mt-9"
    :class="{ 'bg-green-200': buttonClicked }"
    :disabled="buttonClicked"
  >
    play
  </button>
  <GreenBox
    @dont-display-green-box="dontDisplayGreenBox"
    v-if="displayGreenBox"
  />
  <p v-show="showTime">time: {{ score }}</p>
</template>

<script setup>
import { ref } from "vue";
import GreenBox from "./components/GreenBox.vue";
let buttonClicked = ref(false);
let displayGreenBox = ref(false);
let score = ref(0);
let showTime = ref(false);
let delay = 1000;
// + Math.random() * 5000;
function waitASec() {
  buttonClicked.value = true;
  showTime.value = false;
  setTimeout(() => {
    displayGreenBox.value = true;
  }, delay);
}
function dontDisplayGreenBox(time) {
  displayGreenBox.value = !displayGreenBox.value;
  buttonClicked.value = !buttonClicked.value;
  score.value = time;
  showTime.value = true;
}
</script>
