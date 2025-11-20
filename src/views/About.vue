<script setup>

import Header from "@/layouts/Header.vue";
import Footer from "@/layouts/Footer.vue";
import Hero from "@/layouts/Hero.vue";
import HeroPic from "@/assets/images/hero/hero-about.jpg"
</script>

<template>
  <Header />
  <Hero title="О нас" :pathImage="HeroPic"/>
  <Footer />
</template>

<style scoped lang="scss">

</style>