<script setup>
import { defineProps } from "vue";

const props = defineProps({
  income: {
    type: Number,
    required: true,
  },
  expense: {
    type: Number,
    required: true,
  },
});
</script>

<template>
  <div
    class="flex items-center justify-between w-[250px] px-6 py-2 rounded-md border border-gray-300"
  >
    <div>
      <h4 class="font-semibold">Income</h4>
      <p class="text-green-400">+${{ income }}</p>
    </div>

    <div class="w-[2px] bg-gray-400 h-10"></div>
    <div>
      <h4 class="font-semibold">Expense</h4>
      <p class="text-red-400">${{ expense }}</p>
    </div>
  </div>
</template>
