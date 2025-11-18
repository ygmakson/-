<script setup>

</script>

<template>
<button>
  <span>
    <slot></slot>
  </span>
</button>
</template>

<style
    scoped
    lang="scss"
>
@use '@/styles/helpers' as *;
button {
  position: relative;
  font-size: fluid(20,16);
  font-weight: 500;
  color: var(--white);
  display: flex;
  align-items: center;
  &::after {
    content: '';
    @include square(rem(40));
    background: url("@/assets/images/icons/arrow-btn.svg");
  }
}

</style>