<script setup>
import Header from "@/layouts/Header.vue";
import Hero from "@/layouts/Hero.vue";
import HeroPic from '@/assets/images/hero/hero-main.jpg'
import Button from "@/components/Button.vue";
import PopularProduct from "@/layouts/PopularProduct.vue";
import Advantages from "@/layouts/Advantages.vue";
import Reviews from "@/layouts/Reviews.vue";
import Footer from "@/layouts/Footer.vue";
</script>

<template>
  <Header/>
  <Hero title="Новая коллекция" :pathImage="HeroPic"><router-link to="/catalogue"><Button>
    СМОТРЕТЬ</Button></router-link></Hero>
  <PopularProduct />
  <Advantages />
  <Reviews />
  <Footer />
</template>

<style scoped lang="scss">

</style>