<script setup lang="ts">
import {ref} from "vue";
import Title from "../../components/UI/Title.vue";
import Button from "primevue/button";
import Tag from "primevue/tag";
import Carousel from "primevue/carousel";
import 'primeicons/primeicons.css';
import BuyBtn from "../../components/UI/Buttons/BuyBtn.vue";


type FreeCourse = {
  id: number;
  code: string;
  name: string;
  description: string;
  image: string;
  price: number;
  category: string;
  quantity: number;
  inventoryStatus: string;
  rating: number;
};

const sectionTitle = ref("دوره های رایگان");
const freeCourse = ref<FreeCourse[]>([
  {
    id: 1,
    code: "001",
    name: "13 اصل موفقیت با باب پراکتور",
    description: "13 اصلی که آموزش داده میشه",
    image: "/src/assets/images/lagacy.jpg",
    price: 0,
    category: "توسعه فردی",
    quantity: 100,
    inventoryStatus: "موجود",
    rating: 4,
  },
  {
    id: 2,
    code: "002",
    name: "اسرار مراقبه",
    description: "",
    image: "/src/assets/images/lagacy.jpg",
    price: 0,
    category: "توسعه فردی",
    quantity: 100,
    inventoryStatus: "موجود",
    rating: 4,
  },
  {
    id: 3,
    code: "003",
    name: "13 اصل موفقیت با باب پراکتور",
    description: "13 اصلی که آموزش داده میشه",
    image: "/src/assets/images/lagacy.jpg",
    price: 0,
    category: "توسعه فردی",
    quantity: 100,
    inventoryStatus: "تمام شده",
    rating: 4,
  },
  {
    id: 4,
    code: "004",
    name: "13 اصل موفقیت با باب پراکتور",
    description: "13 اصلی که آموزش داده میشه",
    image: "/src/assets/images/lagacy.jpg",
    price: 0,
    category: "توسعه فردی",
    quantity: 100,
    inventoryStatus: "تمام شده",
    rating: 4,
  },
  {
    id: 5,
    code: "005",
    name: "13 اصل موفقیت با باب پراکتور",
    description: "13 اصلی که آموزش داده میشه",
    image: "/src/assets/images/lagacy.jpg",
    price: 0,
    category: "توسعه فردی",
    quantity: 100,
    inventoryStatus: "تمام شده",
    rating: 4,
  },
]);

const responsiveOptions = ref([
  {
    breakpoint: "1024px",
    numVisible: 3,
    numScroll: 1,
  },
  {
    breakpoint: "768px",
    numVisible: 2,
    numScroll: 1,
  },
  {
    breakpoint: "560px",
    numVisible: 1,
    numScroll: 1,
  },
]);

const getSeverity = (status: string) => {
  switch (status) {
    case "موجود":
      return "success";
    case "محدود":
      return "warning";
    case "تمام شده":
      return "danger";
    default:
      return "info";
  }
};
</script>

<template>
  <Title :title="sectionTitle"/>
  <Carousel :value="freeCourse" :numVisible="3" :numScroll="1" :responsiveOptions="responsiveOptions">
    <template #item="slotProps">
      <div class="dark:bg-zinc-800 dark:border-surface-700 rounded m-2 p-4">
        <div class="mb-4">
          <div class="relative mx-auto">
            <img :src="slotProps.data.image" :alt="slotProps.data.name" class="w-full rounded-xl"/>
            <Tag :value="slotProps.data.inventoryStatus" :severity="getSeverity(slotProps.data.inventoryStatus)"
                 class="absolute" style="left: 5px; top: 5px"/>
          </div>
        </div>
        <div class="mb-4 font-medium text-center">{{ slotProps.data.name }}</div>
        <div class="flex justify-center items-center">
          <BuyBtn :cost="slotProps.data.price"/>
          <span class="flex">
          </span>
        </div>
      </div>
    </template>
  </Carousel>
</template>
