<template lang="pug">
  main.illustrator
    v-container.illustrator__content(tag="section")
      v-row.illustrator__content__row
        v-col.illustrator__content__row__title(v-text="title.toUpperCase()" tag="h1" cols="12")
      v-row.illustrator__content__wrapper
        v-col.illustrator__content__wrapper__item(v-for="illustrator in illustrators" :key="illustrator.src" cols="12" md="4")
          v-card
            v-img(:src="illustrator.src" :alt="illustrator.title")
</template>

<script>
import number01 from '@/assets/images/illustrators/number01.svg'
import number02 from '@/assets/images/illustrators/number02.svg'
import number03 from '@/assets/images/illustrators/number03.svg'
import number04 from '@/assets/images/illustrators/number04.svg'
import number05 from '@/assets/images/illustrators/number05.svg'
import number06 from '@/assets/images/illustrators/number06.svg'
import number07 from '@/assets/images/illustrators/number07.svg'
import number08 from '@/assets/images/illustrators/number08.svg'
import number09 from '@/assets/images/illustrators/number09.svg'
import number10 from '@/assets/images/illustrators/number10.svg'
export default {
  data() {
    return {
      title: 'illustrator',
      illustrators: [
        {title: 'number10', src: number10 },
        {title: 'number09', src: number09 },
        {title: 'number08', src: number08 },
        {title: 'number07', src: number07 },
        {title: 'number06', src: number06 },
        {title: 'number05', src: number05 },
        {title: 'number04', src: number04 },
        {title: 'number03', src: number03 },
        {title: 'number02', src: number02 },
        {title: 'number01', src: number01 },
      ],
    }
  },
  methods: {
    toPage (url) {
      location.href = url
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.illustrator {
  padding: $header-height 0;
  background-color: $main-color;
  color: $light-color;
  min-height: 100vh;
  &__content {
    &__row {
      &__title {
        text-align: center;
        padding: 0 $side-space;
        @include title;
      }
    }
    &__wrapper {
      &__item {
        .v-card {
          color: $dark-color;
          background-color: $light-color;
          display: flex;
          .v-image {
            filter: drop-shadow(1px 1px 1px $dark-color);
          }
          &__text {
            transform: translateX(3%);
          }
        }
      }
    }
  }
}
</style>
