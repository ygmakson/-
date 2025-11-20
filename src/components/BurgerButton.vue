<script setup>
import {ref} from "vue";

const emit = defineEmits(['openBurger'])
const burgerActive = ref(false)
function openBurger() {
  burgerActive.value = !burgerActive.value
  emit('openBurger', burgerActive.value)
}
</script>

<template>
  <button @click="openBurger" class="burger-button" :class="{burgerClose: burgerActive}">
    <div class="burger-button__wrapper">
      <span class="burger-button__span"></span>
      <span class="burger-button__span"></span>
      <span class="burger-button__span"></span>
    </div>
  </button>
</template>

<style scoped lang="scss">
@use '@/styles/helpers' as *;
.burger-button {
  @include tablet-above {
    @include visually-hidden
  }
  @include square(rem(40));
  position: relative;
  padding: rem(5);
  transition-duration: .2s;
  &__wrapper {
    position: absolute;
    display: flex;
    flex-direction: column;
    width: rem(30);
    height: rem(30);
    gap: .5rem;
    position: relative;
  }
  &__span {
    display: block;
    width: 100%;
    height: rem(2);
    background-color: var(--beige);
  }
}
.burgerClose {
  transition-duration: .2s;
  span {
    transition-duration: .2s;
    &:last-child {
      transform: scaleX(0);
    }
    &:first-child {
      position: absolute;
      @include abs-center;
      transform: rotateZ(45deg);
    }
    &:nth-child(2) {
      position: absolute;
      @include abs-center;
      transform: rotateZ(-45deg);
    }
  }
}
</style>
