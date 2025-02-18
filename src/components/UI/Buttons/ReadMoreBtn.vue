<script setup lang="ts">
defineProps<{link : string}>();
</script>

<template>
  <a
      :href="link"
      target="_blank"
      class="inline-flex items-center px-3 py-2 my-2 text-sm font-medium text-center text-zinc-100 bg-teal-700 rounded-lg hover:bg-teal-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-teal-600 dark:hover:bg-teal-700 dark:focus:ring-teal-800 transition-all"
  >
    ادامه مطالب
    <svg
        class="rtl:rotate-180 w-3.5 h-3.5 ms-2"
        aria-hidden="true"
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 14 10"
    >
      <path
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M1 5h12m0 0L9 1m4 4L9 9"
      />
    </svg>
  </a>
</template>

<style scoped>

</style>