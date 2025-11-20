<script setup lang="ts">

import Adventage from "@/components/Adventage.vue";
import Capsule from '@/assets/images/icons/capsule.svg'
import Clothing from '@/assets/images/icons/clothing.svg'
import Delivery from '@/assets/images/icons/delivery.svg'
const adventages = [
  {head: 'Капсульная эстетика', text: 'Коллекции «Монохрома» построены на чистых линиях и нейтральных тонах — вещи легко сочетаются и позволяют собрать продуманный базовый гардероб.'},
  {head: 'Персональный подбор стиля', text: 'Стилист-консультанты помогают клиентам находить образы под задачи и типаж, делая покупки точными и продуманными.'},
  {head: 'Быстрая доставка по всей стране', text: 'Заказы отправляются в день оформления, а доставка занимает минимальное время — клиенты получают вещи без долгого ожидания.'},
]

</script>

<template>
  <section class="adventages">
    <div class="adventages__inner container">
      <h2 class="adventages__head">Наши преимущества</h2>
      <div class="adventages__list">
        <Adventage :head="adventages[0].head" :text="adventages[0].text"><Capsule :style="{stroke: 'var(--black)'}" /></Adventage>
        <Adventage :head="adventages[1].head" :text="adventages[1].text"><Clothing class="adventages__icon" /></Adventage>
        <Adventage :head="adventages[2].head" :text="adventages[2].text"><Delivery class="adventages__icon" /></Adventage>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
@use '@/styles/helpers' as *;
.adventages {
  margin-top: fluid(48, 32);
  &__inner {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }
  &__list {
    display: flex;
    align-items: center;
    gap: fluid(16, 8);
    flex-wrap: wrap;
    justify-content: center;
  }

  &__icon {
    min-width: rem(70);
    min-height: rem(70);
    fill: var(--black);
  }
}
</style>