<template>
  <div>
    <input v-model="searchKey" class="border border-black" type="text" />
    <p class="border-b-2">{{ searchKey }}</p>
  </div>
  <p v-for="item in selectedItems" :key="item">{{ item }}</p>
</template>

<script setup>
import { computed } from "@vue/reactivity";
import { onMounted, ref, watch } from "vue";
let searchKey = ref(null);
let array = ref(["bishant", "suman", "ruman", "rishi", "rambo"]);
const selectedItems = computed(() => {
  return array.value.filter((item) => item.includes(searchKey.value));
});
</script>

<style lang="scss" scoped></style>
