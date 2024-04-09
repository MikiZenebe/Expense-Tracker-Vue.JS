<script setup>
import Header from "./components/Header.vue";
import Balance from "./components/Balance.vue";
import IncomeExpenses from "./components/IncomeExpenses.vue";
import TransactionList from "./components/TransactionList.vue";
import AddTransaction from "./components/AddTransaction.vue";

import { ref, computed, onMounted } from "vue";

const transactions = ref([]);

//Like UseEffect
onMounted(() => {
  const savedTransaction = JSON.parse(localStorage.getItem("transactions"));

  if (savedTransaction) {
    transactions.value = savedTransaction;
  }
});

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

//Add Transaction
const handleTransactionSubmitted = (transactionData) => {
  transactions.value.push({
    id: generateUniqueId(),
    text: transactionData.text,
    amount: transactionData.amount,
  });
  saveTransactionToLocStorage();
  alert("Transaction added ✔");
};

//Generate unique id
const generateUniqueId = () => {
  return Math.floor(Math.random() * 1000000);
};

//Delete Transaction
const handleDeleted = (id) => {
  transactions.value = transactions.value.filter(
    (transaction) => transaction.id !== id
  );
  saveTransactionToLocStorage();
  alert("Transaction deleted 🧺");
};

//Save to localStorage
const saveTransactionToLocStorage = () => {
  localStorage.setItem("transactions", JSON.stringify(transactions.value));
};
</script>

<template>
  <div class="flex flex-col gap-2 card p-6 rounded-lg shadow-2xl h-auto">
    <Header />
    <Balance :total="total" />
    <IncomeExpenses :income="+income" :expense="+expense" />
    <TransactionList
      :transactions="transactions"
      @transactionDeleted="handleDeleted"
    />
    <AddTransaction @transactionSubmitted="handleTransactionSubmitted" />
  </div>
</template>
