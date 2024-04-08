<script setup></script>

<template>
  <div class="flex flex-col gap-2">
    <h3 class="text-md font-semibold text-slate-500 pt-3 border-b-2">
      Add Transaction
    </h3>
    <div class="flex flex-col gap-1">
      <div>
        <input
          class="w-full transition-all duration-[300ms] ease-out rounded-md appearance-none border border-gray-300 py-0.5 px-2 bg-white text-gray-700 placeholder-gray-400 shadow-sm text-base focus:outline-none focus:ring-2 focus:ring-green-800 focus:border-transparent placeholder:text-sm"
          type="text"
          placeholder="Enter Reason"
        />
      </div>
      <div>
        <input
          class="w-full transition-all duration-[300ms] ease-out rounded-md appearance-none border border-gray-300 py-0.5 px-2 bg-white text-gray-700 placeholder-gray-400 shadow-sm text-base focus:outline-none focus:ring-2 focus:ring-green-800 focus:border-transparent placeholder:text-sm"
          type="text"
          placeholder="Amount (-ve-expense,+ve-expense)"
        />
      </div>

      <button
        class="bg-green-600 mt-6 p-1.5 text-white rounded-md hover:bg-white hover:border hover:border-green-500 hover:text-green-500 transition ease-in"
      >
        Add Transaction
      </button>
    </div>
  </div>
</template>
