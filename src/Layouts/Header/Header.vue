<script setup lang="ts">
import Logo from "../../components/UI/Logo.vue";
import Nav from "./Nav.vue";
import SignupButton from "../../components/UI/Buttons/SignUpBtn.vue";
import MobileMenuBtn from "../../components/UI/Buttons/MobileMenuBtn.vue";
</script>

<template>
  <header class="header dark:bg-zinc-800 min-h-[desired-height]">
    <section
        class="container max-w-7xl mx-auto px-4 flex items-center justify-between"
    >
      <Logo/>
      <Nav class="hidden lg:flex"/>
      <div class="flex items-center space-x-4">
        <SignupButton/>
        <div class="block lg:hidden">
          <MobileMenuBtn/>
        </div>
      </div>
    </section>
  </header>
</template>
