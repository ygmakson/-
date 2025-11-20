<script setup>
defineProps({
  avatar: String,
  age: String,
  name: String,
  surname: String,
  text: String,
  date: String
})
</script>

<template>
<div class="review">
  <div class="review__top">
    <div class="review__userdata">
      <img alt="#" class="review__avatar" :src="avatar">
      <div class="review__userdata-nameage">
        <div class="review__userdata-name">{{name}} {{surname}}</div>
        <div class="review__userdata-age">{{age}}</div>
      </div>
    </div>
    <div class="review__age">{{date}}</div>
  </div>
  <div class="text">{{text}}</div>
</div>
</template>

<style
    scoped
    lang="scss"
>
@use '@/styles/helpers' as *;
.review {
  width: fluid(600, 360);
  background-color: var(--white);
  border: 1px solid var(--gray);
  padding: fluid(32, 16);
  border-radius: 2rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  &__top {
    display: flex;
    align-items: start;
    justify-content: space-between;
  }
  &__userdata {
    display: flex;
    align-items: center;
    gap: rem(8);
    &-nameage {
      display: flex;
      flex-direction: column;
      gap: rem(8);
    }
    &-name {
      font-weight: 500;
      font-size: fluid(24, 18);
    }
    &-age {
      color: var(--black);
      opacity: 50%;
      font-size: fluid(16, 14);
    }
  }
  &__age {
    color: var(--black);
    opacity: 50%;
  }
  &__avatar {
    width: 100%;
    height: auto;
    @include square(fluid(75, 45));
    border-radius: 50%;
  }
}
</style>