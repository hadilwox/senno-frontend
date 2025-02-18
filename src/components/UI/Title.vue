<script setup lang="ts">
defineProps<{ title: string }>();
</script>

<template>
  <div class="title flex justify-center my-8">
    <h2 class="text-2xl font-bold dark:text-zinc-100">{{ title }}</h2>
  </div>
</template>
