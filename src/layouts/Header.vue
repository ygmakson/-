<script setup>
import Logo from '@/assets/images/icons/logo.svg'
import Search from '@/assets/images/icons/search.svg'
import Favorite from '@/assets/images/icons/favorite.svg'
import ShoppingCart from '@/assets/images/icons/shopping-cart.svg'
import Profile from '@/assets/images/icons/profile.svg'
import Moon from '@/assets/images/icons/moon.svg'
import {useRoute} from "vue-router";
import {ref} from "vue";
import BurgerButton from "@/components/BurgerButton.vue";

const darkIsActive = ref(false)


function setDarkTheme() {
  darkIsActive.value = !darkIsActive.value
  console.log(darkIsActive.value)
  const body = document.querySelector('body')
  body.classList.toggle('isDark')
}



const pages = [
  {name: 'главная', path: '/'},
  {name: 'каталог', path: '/catalogue'},
  {name: 'контакты', path: '/contact'},
  {name: 'о нас', path: '/about'},]
const route = useRoute()
const burgerOpen = ref(false)
function openBurgerMenu(state) {
  burgerOpen.value = state
  console.log(`Меню открыто: ${burgerOpen.value}`)
}
</script>

<template>
  <header class="header">
    <div class="header__inner container">
      <router-link  to="/"><Logo class="header__logo"/></router-link>
      <div class="burger-wrapper" :class="{burgerMenuOpen: burgerOpen}">
        <nav class="header__nav">
          <router-link v-for="page in pages"
                       :to="page.path"
                       :key="page.name"
                       :class="{activePage: route.path === page.path}"
                       class="header__nav-link"
          >{{page.name}}</router-link>
        </nav>
        <div class="header__buttons">
          <button @click="setDarkTheme"><Moon class="header__buttons-icon"/></button>
          <button><Search class="header__buttons-icon"/></button>
          <button><Favorite class="header__buttons-icon"/></button>
          <button><ShoppingCart class="header__buttons-icon"/></button>
          <button class="header__buttons-profile">
            Войти
            <Profile class="header__buttons-icon"/>
          </button>
        </div>
      </div>
      <BurgerButton @openBurger="openBurgerMenu" />
    </div>
  </header>
</template>

<style scoped lang="scss">
@use '@/styles/helpers' as *;
  .header {
    position: fixed;
    z-index: 100;
    background-color: var(--white);
    width: 100vw;
    animation: scrolling-header linear;
    animation-timeline: scroll();
    animation-range: 0px 100px;

    @keyframes scrolling-header {
      from {
        transform: translateY(-101%);
      }
      to {
        top: 0;
      }
    }
    &__inner {
      padding-block: .5rem;
      justify-content: space-between;
      align-items: center;
      display: flex;
    };
    &__nav {
      display: flex;
      gap: 2rem;
      &-link {
        padding-block: .5rem;
        text-transform: uppercase;
        transition-duration: .2s;
        &:not(.activePage) {
          @include hover() {
            color: var(--beige);
          }
        }
      }
    }
    &__logo {
      width: #{fluid(158, 108)};
      height: auto;
      fill: var(--black);
    }
    &__buttons {
      display: flex;
      align-items: center;
      gap: 1rem;
      &-icon{
        fill: var(--black);
        transition-duration: .2s;
        @include hover() {
          fill: var(--beige);
        };
      }
      &-profile {
        display: flex;
        align-items: center;
        gap: .5rem;
        transition-duration: .2s;
        @include hover() {
          fill: var(--beige);
          color: var(--beige);
        };
      }
    }
  }

.burger-wrapper {

  @include tablet-above {
    display: contents;
  }
  @include tablet {
    transition-duration: .2s;
    position: fixed;
    inset-inline: 0;
    top: 0;
    height: 50vh;
    padding: 1rem;
    background-color: var(--white);
    &:not(.burgerMenuOpen) {
      display: none;
      transform: translateX(100%);
    }
  }
}
.burgerMenuOpen {
  transition-duration: .2s;
  display: block;
  transform: translateX(0);
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  justify-content: center;
  gap: 3rem;

  .header__nav {
    flex-direction: column;
    align-items: center;
  }
}

</style>