<script setup lang="ts">
import { ref } from "vue";
import Logo from "../../components/UI/Logo.vue";

interface FooterLink {
  text: string;
  url: string;
}

interface FooterSection {
  title: string;
  links: FooterLink[];
}

const footerData = ref<FooterSection[]>([
  {
    title: "دوره ها",
    links: [
      { text: "بیزینس کوچ", url: "https://flowbite.com/" },
      { text: "ذهن خود آگاه", url: "https://tailwindcss.com/" },
    ],
  },
  {
    title: "ارتباط با ما",
    links: [
      { text: "اینستاگرام", url: "https://instagram.com" },
      { text: "تلگرام", url: "https://t.me" },
    ],
  },
  {
    title: "کاربر",
    links: [
      { text: "قوانین استفاده از دوره ها", url: "#" },
      { text: "ثبت نام و ورود", url: "#" },
    ],
  },
]);
</script>

<template>
  <footer class="bg-white dark:bg-zinc-800 mt-10">
    <div class="mx-auto w-full max-w-screen-xl p-4 py-6 lg:py-8">
      <div class="md:flex md:justify-between">
        <div class="mb-6 md:mb-0">
          <Logo />
        </div>
        <div class="grid grid-cols-2 gap-8 sm:gap-6 sm:grid-cols-3">
          <div v-for="(section, index) in footerData" :key="index">
            <h2 class="mb-6 text-sm font-semibold text-zinc-900 uppercase dark:text-zinc-100">
              {{ section.title }}
            </h2>
            <ul class="text-zinc-500 dark:text-zinc-400 font-medium">
              <li v-for="(link, idx) in section.links" :key="idx" class="mb-4">
                <a :href="link.url" class="hover:underline">{{ link.text }}</a>
              </li>
            </ul>
          </div>
        </div>
      </div>
      <hr class="my-6 border-zinc-200 sm:mx-auto dark:border-zinc-700 lg:my-8" />
      <div class="sm:flex sm:items-center sm:justify-between">
        <span class="text-sm text-zinc-500 sm:text-center dark:text-zinc-400">
          تمامی قوانین این سایت متعلق است به
          <a href="#" class="hover:underline">Senno</a>
        </span>
      </div>
    </div>
  </footer>
</template>
