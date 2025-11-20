<script setup lang="ts">
import {ref} from 'vue';
import Button from "@/components/Button.vue";

const data = ref([
  {name: 'Кардиган из шерсти', rate: 4.8, otzivi: 55, price: '4 999', pathPic: new URL('@/assets/images/cards/card1.jpg', import.meta.url).href},
  {name: 'Кардиган из шерсти', rate: 4.8, otzivi: 55, price: '4 999', pathPic: new URL('@/assets/images/cards/card2.jpg', import.meta.url).href},
  {name: 'Кардиган из шерсти', rate: 4.8, otzivi: 55, price: '4 999', pathPic: new URL('@/assets/images/cards/card3.jpg', import.meta.url).href},
  {name: 'Кардиган из шерсти', rate: 4.8, otzivi: 55, price: '4 999', pathPic: new URL('@/assets/images/cards/card4.jpg', import.meta.url).href}
])
</script>

<template>
  <section class="popular">
    <div class="container">
      <h2 class="popular__head">Популярные товары</h2>
    </div>
    <div class="popular__cards">
      <div v-for="card in data" class="popular__card" :key="card.pathPic">
        <div class="popular__card-img">
          <img :src="card.pathPic" alt="card" />
        </div>
        <div class="popular__card-info">
          <div class="popular__card-info-top">
            <h3>{{card.name}}</h3>
            <p>{{card.rate}} - {{card.otzivi}} отзыв</p>
          </div>
          <div class="popular__card-info-bottom">
            <h3>{{card.price}} руб.</h3>
            <Button class="popular__card-btn">Перейти на страницу товара</Button>
          </div>
        </div>
      </div>
      <button class="popular__btn"></button>
    </div>
  </section>
</template>

<style scoped lang="scss">
@use '@/styles/helpers' as *;
  .popular {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    padding-block: 2rem;
    &__cards {
      display: flex;
      align-items: center;
      justify-content: center;
      overflow-inline: hidden;
      height: max-content;
      gap: fluid(16, 0);
      @include mobile {
        &::after {
          content: '';
          width: 10px;
          height: 20px;
          background: url("@/assets/images/icons/next-card.svg") no-repeat center / contain;
          margin-left: 5px;
        }
        &::before {
          content: '';
          width: 10px;
          height: 20px;
          background: url("@/assets/images/icons/next-card.svg") no-repeat center / contain;
          transform: rotateZ(180deg);
          margin-right: 5px;
        }
      }
    }
    &__card {
      display: flex;
      position: relative;
      @include mobile {
        &::after {
          display: none;
        }
      }
      &:nth-child(1) {
        @include tablet {
          display: none;
        }

        height: 15em;
        &::after {
          border-top-left-radius: rem(32);
          border-bottom-left-radius: rem(32);
          content: '';
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          background-color: #000000;
          opacity: 0.8;

        }
      }
      &:nth-child(2) {
        height: 20em;

        @include mobile {
          display: flex;
          height: auto;
        }
        @include tablet {
          display: none;
        }

        &::after {
          border-top-left-radius: rem(32);
          border-bottom-left-radius: rem(32);
          content: '';
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          background-color: #000000;
          opacity: 0.6;
        }
      }
      &:nth-child(3) {
        height: 25em;

        @include mobile {
          display: flex;
          height: auto;
        }
        @include tablet {
          display: none;

        }
        &::after {
          border-top-left-radius: rem(32);
          border-bottom-left-radius: rem(32);
          content: '';
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          background-color: #000000;
          opacity: 0.4;
        }
      }
      &:nth-child(4) {
        z-index: 2;


      }

      &:not(:first-child) {
        margin-left: fluid(-500, -600);
        @include tablet {
          margin-left: 0;
        }
      }
      &-img {
        border-top-left-radius: rem(32);
        border-bottom-left-radius: rem(32);
        position: relative;
        @include tablet {
          width: 30vw;
        }
        img {
          height: 100%;
          border-top-left-radius: rem(32);
          border-bottom-left-radius: rem(32);

        }
      }
      &-info {
        background-color: var(--white);
        border: 1px solid var(--gray);
        border-left: 0;
        padding: fluid(32, 16);
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        border-top-right-radius: rem(32);
        border-bottom-right-radius: rem(32);
        &:not(:last-child) {
          display: none;
        }
        &-top {
          display: flex;
          flex-direction: column;
          gap: .5rem;

          p {
            opacity: 50%;
            font-size: fluid(32, 12);
            display: flex;
            align-items: center;
            &::before {
              content: '';
              @include square(fluid(30, 15));
              background: url('@/assets/images/icons/star.svg') no-repeat center center/contain;
            }
          }
        }

      }
      &-btn {
        color: var(--black);
        @include tablet {
          display: none;
        }
      }
    }
  &__btn {
    @include square(fluid(50,30));
    background: url("@/assets/images/icons/next-card.svg") no-repeat center / contain;
    @include mobile {
      display: none;
    }
  }
  }
</style>