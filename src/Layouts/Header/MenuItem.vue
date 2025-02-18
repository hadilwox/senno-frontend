<script setup lang="ts">
import { ref } from "vue";

type MenuItem = {
  title: string;
  link?: string;
  submenu?: { title: string; link: string }[];
};

defineProps<{ item: MenuItem }>();

const isOpen = ref(false);

const showSubmenu = () => {
  isOpen.value = true;
};

const hideSubmenu = () => {
  setTimeout(() => {
    if (!isMouseOverSubmenu.value) {
      isOpen.value = false;
    }
  }, 300);
};

const isMouseOverSubmenu = ref(false);
</script>

<template>
  <li
      class="group relative flex items-center px-6 py-4 dark:hover:bg-zinc-700 rounded-3xl cursor-pointer"
      @mouseenter="showSubmenu"
      @mouseleave="hideSubmenu"
  >
    <template v-if="item.link">
      <a :href="item.link" class="dark:text-zinc-100">{{ item.title }}</a>
    </template>

    <template v-else>
      <span class="dark:text-zinc-100">{{ item.title }}</span>
      <ul
          v-if="item.submenu"
          class="absolute left-0 top-full mt-2 p-4 rounded-xl w-40 bg-zinc-800 transition-opacity duration-200 z-[100]"
          :class="{ 'opacity-100 visible': isOpen, 'opacity-0 invisible': !isOpen }"
          @mouseenter="isMouseOverSubmenu = true"
          @mouseleave="isMouseOverSubmenu = false; hideSubmenu()"
      >
      <li
            v-for="(subItem, subIndex) in item.submenu"
            :key="subIndex"
            class="text-zinc-100 py-4 px-4 hover:bg-zinc-700 rounded cursor-pointer"
        >
          <a :href="subItem.link">{{ subItem.title }}</a>
        </li>
      </ul>
    </template>
  </li>
</template>
