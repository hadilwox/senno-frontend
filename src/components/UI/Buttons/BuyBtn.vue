<script setup lang="ts">
defineProps<{
  cost: number | string;
  link?: string;
}>();
</script>

<template>
  <a
      :href="link || '#'"
      class="focus:outline-none text-white bg-teal-700 hover:bg-teal-800 focus:ring-4 focus:ring-teal-300 font-medium rounded-lg text-sm px-8 py-2 me-2 mb-2 dark:bg-teal-600 dark:hover:bg-teal-700 dark:focus:ring-teal-800 transition-all"
  >
    {{ Number(cost) === 0 ? "رایگان" : cost }}
  </a>
</template>
