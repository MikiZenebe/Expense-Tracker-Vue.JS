<script setup>
import Header from "./components/Header.vue";
import Balance from "./components/Balance.vue";
import IncomeExpenses from "./components/IncomeExpenses.vue";
import TransactionList from "./components/TransactionList.vue";
import AddTransaction from "./components/AddTransaction.vue";
</script>

<template>
  <div class="flex flex-col gap-2 card p-12 rounded-lg shadow-2xl h-auto">
    <Header />
    <Balance />
    <IncomeExpenses />
    <TransactionList />
    <AddTransaction />
  </div>
</template>
