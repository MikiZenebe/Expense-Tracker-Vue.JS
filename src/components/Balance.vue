<script setup>
import { defineProps } from "vue";

const props = defineProps({
  total: {
    type: Number,
    required: true,
  },
});
</script>

<template>
  <div>
    <h4 class="text-sm text-slate-500">Your Balance</h4>
    <h1 class="text-md font-semibold text-slate-500">${{ total }}</h1>
  </div>
</template>
