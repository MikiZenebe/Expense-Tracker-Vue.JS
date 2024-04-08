<script setup>
import Header from "./components/Header.vue";
import Balance from "./components/Balance.vue";
import IncomeExpenses from "./components/IncomeExpenses.vue";
import TransactionList from "./components/TransactionList.vue";
import AddTransaction from "./components/AddTransaction.vue";

import { ref, computed } from "vue";

const transactions = ref([
  { id: 1, text: "Flower", amount: -19.99 },
  { id: 2, text: "Salary", amount: 299.97 },
  { id: 3, text: "Books", amount: 25.44 },
  { id: 4, text: "Internet", amount: -119.99 },
]);

//Get the total
const total = computed(() => {
  return transactions.value.reduce((acc, item) => {
    return acc + item.amount;
  }, 0);
});

//Get Income
const income = computed(() => {
  return transactions.value
    .filter((item) => item.amount > 0)
    .reduce((acc, item) => {
      return acc + item.amount;
    }, 0)
    .toFixed(2);
});

//Get Expense
const expense = computed(() => {
  return transactions.value
    .filter((item) => item.amount < 0)
    .reduce((acc, item) => {
      return acc + item.amount;
    }, 0)
    .toFixed(2);
});
</script>

<template>
  <div class="flex flex-col gap-2 card p-12 rounded-lg shadow-2xl h-auto">
    <Header />
    <Balance :total="total" />
    <IncomeExpenses :income="income" :expense="expense" />
    <TransactionList :transactions="transactions" />
    <AddTransaction />
  </div>
</template>
