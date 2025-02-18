<script setup lang="ts">
import {ref} from "vue";
import {Swiper, SwiperSlide} from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";
import {Autoplay, Navigation, Pagination} from "swiper/modules";

const banners = ref([
  "src/assets/images/senno-banner2.png",
  "src/assets/images/RoyalMind1075.jpg",
  "src/assets/images/lagacy.jpg"
]);

const isGrabbing = ref(false);
const handleMouseDown = () => {
    isGrabbing.value = true;
};

const handleMouseUp = () => {
  isGrabbing.value = false;
};

</script>

<template>
  <!-- banner web app -->
  <section class="banner md:max-w-7xl md:mx-auto lg:px-4 lg:mt-8">
    <Swiper
        :modules="[Autoplay, Navigation, Pagination]"
        :loop="true"
        :autoplay="{ delay: 5000 }"
        :navigation="true"
        :pagination="{ clickable: true }"
        class="w-full z-10 max-w-screen-xl bg-zinc-700 lg:rounded-xl mx-auto"
    >
      <SwiperSlide v-for="(img, index) in banners" :key="index">
        <img
            :src="img"
            class="w-full min-h-40 object-cover lg:rounded-xl shadow-lg cursor-grab group-active:cursor-grabbing"
            :class="isGrabbing ? 'cursor-grabbing' : 'cursor-grab'"
            @mousedown="handleMouseDown"
            @mouseup="handleMouseUp"
            @mouseleave="handleMouseUp"
        />
      </SwiperSlide>
    </Swiper>
  </section>
</template>

<style scoped>
.banner {
  overflow: visible !important;
}
</style>