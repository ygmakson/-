<script setup>
import Review from "@/components/Review.vue";

const data = [
  {
    name: 'Марина',
    surname: 'Голубцова',
    age: '28 лет',
    date: '5 дней назад',
    text: 'Первый раз заказывала в “Монохроме” и осталась в восторге. Брала костюм — ткань плотная, посадка идеальная. Доставка быстрая, упаковка минималистичная и стильная. Теперь хочу заказать еще пару вещей к весне.',
    avatar: new URL('@/assets/images/reviews/review1.jpg', import.meta.url).href
  },
  {
    name: 'Максим',
    surname: 'Обмел',
    age: '32 года',
    date: '1 неделю назад',
    text: 'Отличный магазин! Курьер приехал вовремя, вещи полностью соответствуют описанию. Особенно понравился свитер — реально премиальный. Буду заказывать ещё.',
    avatar: new URL('@/assets/images/reviews/review2.jpg', import.meta.url).href
  },
  {
    name: 'Сергей',
    surname: 'Гончаров',
    age: '41 год',
    date: '3 недели назад',
    text: 'Нравится стиль магазина — всё лаконичное и очень качественное. Брал пальто и худи, сели идеально. Радует, что бренд развивается в сторону капсульных коллекций.',
    avatar: new URL('@/assets/images/reviews/review3.jpg', import.meta.url).href
  },
  {
    name: 'Даниил',
    surname: 'Перцов',
    age: '26 лет',
    date: '4 дня назад',
    text: 'Удобно, что сразу видно, как вещи сочетаются друг с другом. Заказал три позиции — собрал полноценный образ. По доставке никаких проблем, всё быстро и аккуратно.',
    avatar: new URL('@/assets/images/reviews/review4.jpg', import.meta.url).href
  },
  {
    name: 'Елизавета',
    surname: 'Брагина',
    age: '24 года',
    date: '6 дней назад',
    text: 'Обожаю минималистичный стиль “Монохрома”. Платье село прекрасно, ткань приятная, швы ровные. Отдельный плюс — очень красивая упаковка, как подарок самой себе.',
    avatar: new URL('@/assets/images/reviews/review5.jpg', import.meta.url).href
  },
]

</script>

<template>
  <section class="reviews">
    <div class="reviews__inner">
      <div class="reviews__head container">
        <h2>Наши отзывы</h2>
      </div>
      <div class="reviews__list-overlay">
        <div class="reviews__list">
          <Review class="review" v-for="user in data"
                  :age="user.age"
                  :avatar="user.avatar"
                  :name="user.name"
                  :surname="user.surname"
                  :date="user.date"
                  :text="user.text"
          />
          <Review class="review" v-for="user in data"
                  :age="user.age"
                  :avatar="user.avatar"
                  :name="user.name"
                  :surname="user.surname"
                  :date="user.date"
                  :text="user.text"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<style
    scoped
    lang="scss"
>
@use '@/styles/helpers' as *;
.reviews {
  background-color: var(--beige-lite);
  border-radius: rem(32);
  overflow: hidden;
  margin-top: 3rem;

  &__inner {
    padding-block: 2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
  }
  &__head {
    align-self: flex-start;
  }
  &__list-overlay {
    overflow: hidden;
    width: 100%;
  }
  &__list {
    display: flex;
    width: max-content;
    animation: slide 50s linear infinite;
    gap: 2rem;

    @keyframes slide {
      0% {
        transform: translateX(0);
      }
      100% {
        transform: translateX(-50%);
      }
    }
  }
}
.review:last-child {
  margin-right: 2rem;
}
</style>