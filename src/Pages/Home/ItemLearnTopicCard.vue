<script setup lang="ts">
import ReadMoreBtn from "../../components/UI/Buttons/ReadMoreBtn.vue";
import {ref} from "vue";

const props = defineProps<{
  topic: {
    id: number;
    title: string;
    image: string;
    link: string;
  };
}>();

const bgColor = ref("bg-white dark:bg-zinc-800");

const getRandomColor = () => {
  const colors = [
    "bg-gradient-to-r from-blue-500 via-blue-600 to-blue-700",
    "bg-gradient-to-r from-green-400 via-green-500 to-green-600",
    "bg-gradient-to-r from-cyan-400 via-cyan-500 to-cyan-600",
    "bg-gradient-to-r from-teal-400 via-teal-500 to-teal-600",
    "bg-gradient-to-r from-lime-200 via-lime-400 to-lime-500",
    "bg-gradient-to-r from-red-400 via-red-500 to-red-600",
    "bg-gradient-to-r from-pink-400 via-pink-500 to-pink-600",
    "bg-gradient-to-r from-purple-500 via-purple-600 to-purple-700",
  ];
  return colors[Math.floor(Math.random() * colors.length)];
};

const changeBackground = () => {
  bgColor.value = getRandomColor();
};

const resetBackground = () => {
  bgColor.value = "bg-white dark:bg-zinc-800";
}
</script>

<template>
  <div :key="topic.id">
    <div
        :class="bgColor"
        class="max-w-full sm:max-w-sm p-6 flex justify-center items-center flex-col border border-zinc-200 rounded-lg shadow-sm dark:border-zinc-700 transition-all duration-300 cursor-pointer"
        @mouseenter="changeBackground"
        @mouseleave="resetBackground"
    >
      <div class="my-2">
        <img
            class="w-20 h-20"
            :src="topic.image || '/default-image.png'"
            :alt="topic.title || 'تصویر نامشخص'"
        />
      </div>
      <a :href="topic.link || '#' " target="_blank" class="my-2">
        <h5
            class="mb-2 text-xl text-center font-bold tracking-tight text-zinc-900 dark:text-zinc-100"
        >
          {{ topic.title }}
        </h5>
      </a>
      <ReadMoreBtn :link="topic.link || '#' "/>
    </div>
  </div>
</template>
