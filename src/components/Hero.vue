<script setup>
defineProps({
  title: String,
  pathImage: String
})
</script>

<template>
<section class="hero" :style="{backgroundImage: `url(${pathImage})`}">
  <div class="hero__inner container"><h1 class="hero__title">{{title}}</h1>
    <slot></slot></div>

</section>

</template>

<style scoped lang="scss">
@use '@/styles/helpers' as *;
.hero {
  height: 100vh;
  width: 100vw;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  &__inner {
    height: 100%;
    display: flex;
    flex-direction: column;
    gap: fluid(40, 30);
    justify-content: center;
    align-items: center;
    text-align: center;
    font-size: fluid(64, 40);
    white-space: wrap;
    font-weight: 600;
    text-transform: uppercase;
  }
  &__title {
    color: var(--white);
  }
}
</style>