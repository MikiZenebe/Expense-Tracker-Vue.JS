<script setup>
import { ref } from "vue";

const text = ref("");
const amount = ref("");

const emit = defineEmits(["transaction submitted"]);

const onSubmit = () => {
  if (!text.value || !amount.value) {
    alert("Both fields must be filled");
    return;
  }

  const transactionData = {
    text: text.value,
    amount: parseFloat(amount.value),
  };
  emit("transactionSubmitted", transactionData);

  text.value = "";
  amount.value = "";
};
</script>

<template>
  <div class="flex flex-col gap-2">
    <h3 class="text-sm font-semibold text-slate-500 pt-3 border-b-2">
      Add Transaction
    </h3>
    <form class="flex flex-col gap-1" @submit.prevent="onSubmit">
      <div>
        <input
          class="w-full transition-all duration-[300ms] ease-out rounded-md appearance-none border border-gray-300 py-0.5 px-2 bg-white text-gray-700 placeholder-gray-400 shadow-sm text-base focus:outline-none focus:ring-2 focus:ring-green-800 focus:border-transparent placeholder:text-xs"
          type="text"
          placeholder="Enter Reason"
          v-model="text"
        />
      </div>
      <div>
        <input
          class="w-full transition-all duration-[300ms] ease-out rounded-md appearance-none border border-gray-300 py-0.5 px-2 bg-white text-gray-700 placeholder-gray-400 shadow-sm text-base focus:outline-none focus:ring-2 focus:ring-green-800 focus:border-transparent placeholder:text-xs"
          type="text"
          placeholder="Amount (-ve-expense,+ve-expense)"
          v-model="amount"
        />
      </div>

      <button
        class="bg-green-600 mt-6 p-1.5 text-white rounded-md hover:bg-white hover:border hover:border-green-500 hover:text-green-500 transition ease-in"
      >
        Add Transaction
      </button>
    </form>
  </div>
</template>
./Modal/Success.js
