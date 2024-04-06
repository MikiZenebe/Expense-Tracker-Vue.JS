<script setup>
import Header from "./components/Header.vue";
import Balance from "./components/Balance.vue";
import IncomeExpenses from "./components/IncomeExpenses.vue";
import TransactionList from "./components/TransactionList.vue";
</script>

<template>
  <div class="flex flex-col gap-2 card p-20 rounded-lg shadow-2xl">
    <Header />
    <Balance />
    <IncomeExpenses />
    <TransactionList />
  </div>
</template>
