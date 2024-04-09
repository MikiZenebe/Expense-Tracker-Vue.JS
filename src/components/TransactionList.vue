<script setup>
import { defineProps } from "vue";
const emit = defineEmits(["transactionDeleted"]);

const props = defineProps({
  transactions: {
    type: Array,
    required: true,
  },
});

const deleteTransaction = (id) => {
  emit("transactionDeleted", id);
};
</script>

<template>
  <div class="flex flex-col gap-2">
    <h3 class="text-sm font-semibold text-slate-500 pt-3 border-b-2">
      History
    </h3>
    <ul class="flex flex-col gap-1">
      <li
        v-for="item in transactions"
        class="bg-slate-100 p-1 items-center text-[13px] flex justify-between relative font-medium"
        :class="item.amount < 0 ? 'minus' : 'plus'"
      >
        {{ item.text }}
        <span
          >${{ item.amount }}
          <button
            class="absolute -right-4 opacity-0 bg-red-500 p-0.5 text-white hover:opacity-100 transition-opacity"
            @click="deleteTransaction(item.id)"
          >
            X
          </button></span
        >
      </li>
    </ul>
  </div>
</template>
