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
  &:hover {
    transition: all .2s;
    color: var(--beige);
  }

  width: fit-content;
  position: relative;
  font-size: fluid(20,14);
  font-weight: 500;
  color: var(--white);
  display: flex;
  align-items: center;
  &::after {
    content: '';
    @include square(fluid(30,20));
    background: url('@/assets/images/icons/arrow-btn.svg') no-repeat center / contain;

  }
}

</style>