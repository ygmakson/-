<script setup>
import Logo from '@/assets/images/icons/logo.svg'
import Zen from '@/assets/images/icons/zen.svg'
import Vk from '@/assets/images/icons/vk.svg'
import Tg from '@/assets/images/icons/tg.svg'
</script>

<template>
<footer class="footer">
  <div class="footer__inner container">

    <Logo class="footer__logo"/>
    <div class="footer__column">
      <b>Контакты:</b>
      <div class="footer__column-data">
        <p>г. Москва, ул. Примерная, 10</p>
        <p>info@monochrome.store</p>
        <p>+7 (000) 000-00-00</p>
      </div>

    </div>
    <div class="footer__column">
      <b>Разделы:</b>
      <div class="footer__column-data">
        <router-link to="#">Каталог</router-link>
        <router-link to="#">Новинки</router-link>
        <router-link to="#">Доставка и возврат</router-link>
        <router-link to="#">Контакты</router-link>
        <router-link to="#">Личный кабинет</router-link>
      </div>
    </div>
    <div class="footer__society">
      <b>Мы в соцсетях</b>
      <div class="footer__society-icons">
        <router-link to="/"><Zen class="zen"/></router-link>
        <router-link to="/"><Vk class="vk"/></router-link>
        <router-link to="/"><Tg class="tg"/></router-link>
      </div>
    </div>
  </div>
  <p class="footer__copyright">© 2025 “монохром”. Все права защищены.</p>
</footer>
</template>

<style
    scoped
    lang="scss"
>
@use '@/styles/helpers' as *;
.footer {
  position: relative;
  background-color: var(--gray-lite);
  border-top-left-radius: rem(32);
  border-top-right-radius: rem(32);
  margin-top: 3rem;
  &__inner {
    display: flex;
    justify-content: space-between;
    padding-block: 2rem;
    @include tablet {
      flex-direction: column;
      gap: 1rem;
    }
  }
  &__logo {
    width: fluid(200, 150)
  }
  &__column {
    display: flex;
    flex-direction: column;
    gap: .5rem;
    &-data {
      display: flex;
      flex-direction: column;
      gap: .5rem;
      @include tablet {
        flex-direction: row;
        gap: 1rem;
        flex-wrap: wrap;
      }
    }
  }
  &__society {
    &-icons {
      display: flex;
      gap: .5rem;
    }
  }

}

.zen {
  transition: all .2s;
  @include hover {
    fill: var(--beige);
  }
}

.vk {
  transition: all .2s;
  @include hover {
    fill: #3f8cff;
  }
}

.tg {
  transition: all .2s;
  @include hover {
    fill: #3fccff;
  }
}
</style>