<script setup></script>

<template>
  <div class="flex flex-col gap-2">
    <h3 class="text-md font-semibold text-slate-500 pt-3 border-b-2">
      History
    </h3>
    <ul class="flex flex-col gap-1">
      <li
        class="bg-slate-100 border-l-4 border-red-500 p-1 items-center text-[15px] font-semibold flex justify-between relative"
      >
        Cash
        <span
          >-$400
          <button
            class="absolute -right-4 opacity-0 bg-red-500 p-0.5 text-white hover:opacity-100 transition-opacity"
          >
            X
          </button></span
        >
      </li>
      <li
        class="bg-slate-100 border-l-4 border-green-400 p-1 text-[15px] font-semibold flex justify-between relative"
      >
        Paycheck
        <span
          >$800
          <button
            class="absolute -right-4 opacity-0 bg-red-500 p-0.5 text-white hover:opacity-100 transition-opacity"
          >
            X
          </button></span
        >
      </li>
    </ul>
  </div>
</template>
