<script setup>
import { ref } from "vue";
defineProps({
  showModal: Boolean,
  userName: String,
});
const emit = defineEmits(["closeModal"]);
function closeModal() {
  emit("closeModal");
  console.log("closeModal function run");
}
</script>
<template>
  <div
    v-show="showModal"
    @click.self="closeModal"
    class="absolute inset-0 flex items-center justify-center min-h-screen min-w-min bg-slate-400"
  >
    <div class="px-16 py-10 bg-green-300 rounded-lg">
      <h1 class="block text-6xl text-white w-max pb-7">
        Hello, {{ userName }}
      </h1>
      <div class="text-center">Nice stuff</div>
    </div>
  </div>
</template>
