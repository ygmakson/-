<script setup lang="ts">
defineProps({
  head: String,
  text: String
})
</script>

<template>
  <div class="adventage">
    <div class="adventage__head">
      <slot></slot>
      <h4>{{head}}</h4>
    </div>
    <div class="adventage__text">
      {{text}}
    </div>
  </div>
</template>

<style scoped lang="scss">
@use '@/styles/helpers' as *;
slot {
  width: fluid(70, 35);
  height: fluid(70, 35);
}
.adventage {
  border-radius: rem(32);
  border: rem(1) solid var(--gray);
  padding: fluid(32, 16);
  display: flex;
  flex-direction: column;
  gap: rem(10);
  width: 100%;
  &__head {
    display: flex;
    align-items: center;
  }
}
</style>