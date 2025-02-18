<script setup lang="ts">
import BuyBtn from "../../components/UI/Buttons/BuyBtn.vue";

const props = defineProps<{
  freeCourse: {
    id: number;
    title: string;
    image: string;
    link: string;
    cost: number;
  };
}>();
</script>

<template>
  <!-- item for learn -->
  <div>
    <div
        class="max-w-full sm:max-w-80 p-6 flex justify-center items-center flex-col bg-white border border-zinc-200 rounded-lg shadow-sm dark:bg-zinc-800 dark:border-zinc-700 dark:hover:bg-zinc-800/70 transition-all"
    >
      <div class="my-2">
        <a :href="props.freeCourse.link">
          <img
              class="rounded-xl"
              :src="props.freeCourse.image"
              :alt="props.freeCourse.title"
          />
        </a>
      </div>
      <a href="#" class="my-2">
        <h5
            class="mb-2 text-lg text-center font-medium tracking-tight text-zinc-900 dark:text-zinc-100 "
        >
          {{ props.freeCourse.title }}
        </h5>
      </a>
      <BuyBtn :cost="props.freeCourse.cost" :link="props.freeCourse.link" />
    </div>
  </div>
</template>

<style scoped>

</style>