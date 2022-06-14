<template>
  <button @click="stopTimer" class="block mx-auto mt-24 bg-green-400 w-72 h-72">
    Click me
  </button>
</template>

<script setup>
import { onMounted, ref } from "vue";
let time = ref(0);
let timer = ref(null);
const emit = defineEmits(["dontDisplayGreenBox"]);
onMounted(() => {
  startTimer();
});
function startTimer() {
  timer.value = setInterval(() => {
    time.value++;
    // console.log(time.value);
  }, 1);
}
function stopTimer() {
  clearInterval(timer.value);
  emit("dontDisplayGreenBox", time.value);
  console.log(time.value);
}
</script>
