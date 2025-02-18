<script setup lang="ts">
const siteName = import.meta.env.VITE_SITE_NAME
</script>

<template>
  <div class="nav-logo py-4">
    <a
      href="#"
      class="dark:text-zinc-100 text-2xl sm:text-3xl lg:text-4xl font-bold"
    >
      <h1>{{siteName}}</h1>
    </a>
  </div>
</template>
