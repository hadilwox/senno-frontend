<script setup lang="ts">
import {ref} from "vue";
import Title from "../../components/UI/Title.vue";
import ItemLearnTopicCard from "./ItemLearnTopicCard.vue";

type LearningTopic = {
  id: number;
  title: string;
  image: string;
  link: string;
};

const sectionTitle = ref("موضوعات یادگیری senno");
const topics = ref<LearningTopic[]>([
  {
    id: 1,
    title: "هدف گذاری و برنامه ریزی سالانه + عادت",
    image: "/src/assets/images/target (1).png",
    link: "#",
  },
  {
    id: 2,
    title: "ذهن خود آگاه و مراقبه توان بخشی",
    image: "/src/assets/images/philosophy.png",
    link: "#",
  },
  {
    id: 3,
    title: "برنامه نویسی و کامپیوتر",
    image: "/src/assets/images/computer.png",
    link: "#",
  }
]);
</script>

<template>
  <!-- Learning topics -->
  <section class="mt-20 container max-w-7xl mx-auto px-4 flex flex-col justify-center">
    <Title :title="sectionTitle"/>
    <div class="content my-6">
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
        <template v-for="topic in topics" :key="topic.id">
          <ItemLearnTopicCard :topic="topic"/>
        </template>
      </div>
    </div>
  </section>
</template>

<style scoped>
</style>
