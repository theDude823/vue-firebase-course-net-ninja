<script setup>
import { ref, reactive } from "vue";
import ModalVue from "./components/Modal.vue";

let userName = ref("bishant");
let showModal = ref(false);
function toggleModal() {
  showModal.value = !showModal.value;
}
</script>

<template>
  <div class="text-center">
    <h1 class="mx-auto mt-10 text-6xl border-b-4 w-max pb-7">
      My first vue app
    </h1>
    <button
      @click="toggleModal"
      class="px-3 py-2 mt-6 bg-green-400 rounded-full"
    >
      Open modal
    </button>
  </div>
  <ModalVue
    @close-modal="toggleModal"
    :showModal="showModal"
    :userName="userName"
  />
</template>
