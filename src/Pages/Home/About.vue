<script setup lang="ts">
import ReadMoreBtn from "../../components/UI/Buttons/ReadMoreBtn.vue";
import Title from "../../components/UI/Title.vue";
import {ref} from "vue";

type AboutSenno = {
  title: string;
  image: string;
  link: string;
  description: string;
};
const aboutSenno = ref<AboutSenno>(
  {
    title: "13 اصل موفقیت با باب پراکتور",
    image: "/src/assets/images/senno-banner2.png",
    link: "#",
    description: "\n" +
        "              مجموعه آموزشی Senno (یا 999) با هدف توانمندسازی افراد در مسیر\n" +
        "              رشد و موفقیت فردی و حرفه‌ای تأسیس شده است. ما در این مجموعه\n" +
        "              تلاش می‌کنیم تا با ارائه دوره‌های آموزشی متنوع، بستری را فراهم\n" +
        "              کنیم که هر فرد بتواند مهارت‌های لازم برای دستیابی به اهداف\n" +
        "              شخصی و شغلی خود را کسب کند. در Senno، ما اعتقاد داریم که\n" +
        "              یادگیری هیچ مرزی ندارد و ذهن انسان توانایی بی‌پایانی برای رشد\n" +
        "              و تحول دارد. به همین دلیل، حوزه‌های آموزشی ما شامل: مهارت‌های\n" +
        "              ذهنی و مراقبه برای دستیابی به آرامش و تمرکز کوچینگ و توسعه\n" +
        "              فردی برای شکوفایی استعدادها مهارت‌های بیزینس و فروش برای کسب\n" +
        "              موفقیت حرفه‌ای برنامه‌نویسی و نرم‌افزار برای ورود به دنیای\n" +
        "              فناوری آموزش‌های تخصصی کامپیوتر برای تقویت توانایی‌های فنی هدف\n" +
        "              ما این است که هر فرد با هر پیشینه‌ای بتواند مسیری روشن برای\n" +
        "              پیشرفت خود بیابد و در این مسیر از دانش و تجربه ما بهره‌مند\n" +
        "              شود. با Senno، راه رشد برای شما باز است. 🌟\n" +
        "            ",
  }
);
</script>

<template>
  <!-- About Senno -->
  <section
      class="mt-20 container max-w-7xl mx-auto px-4 flex flex-col justify-center"
  >
    <Title :title="aboutSenno.title"/>
    <div class="content my-6">
      <div class="flex flex-col lg:flex-row items-center justify-between">
        <div
            class="video-about max-w-full sm:max-w-sm md:max-w-md lg:max-w-xl"
        >
          <div>
            <img
                class="rounded-2xl"
                :src="aboutSenno.image"
                :alt="aboutSenno.title"
            />
          </div>
        </div>
        <div class="text-about max-w-full mt-10 lg:mt-0 lg:max-w-xl">
          <div>
            <p class="text-sm/6 text-zinc-100 text-justify">{{aboutSenno.description}}</p>
          </div>
          <div class="about-btn">
            <ReadMoreBtn :link="aboutSenno.link"/>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>