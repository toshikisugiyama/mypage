<template>
<main class="illustrator">
  <v-container class="illustrator__content" tag="section">
    <v-row class="illustrator__content__row">
      <v-col v-text="title.toUpperCase()" tag="h1" cols="12" class="illustrator__content__row__title" />
    </v-row>
    <v-row class="illustrator__content__wrapper">
      <v-col v-for="illustrator in illustrators" :key="illustrator.src" class="illustrator__content__wrapper__item" cols="12" md="4">
        <v-card>
          <v-img :src="illustrator.src" :alt="illustrator.title" />
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</main>
</template>

<script>
import number01 from '@/assets/images/illustrators/number01.svg'
import number02 from '@/assets/images/illustrators/number02.svg'
import number03 from '@/assets/images/illustrators/number03.svg'
import number04 from '@/assets/images/illustrators/number04.svg'
export default {
  data() {
    return {
      title: 'illustrator',
      illustrators: [
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
