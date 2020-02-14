<template>
  <main class="main" >
    <section class="main__top">
      <v-container class="main__top__container">
        <v-row class="main__top__container__row">
          <v-col
            v-text="name.en"
            tag="h1"
            cols="12"
            class="main__top__container__row__title"
          />
          <v-col
            v-text="name.ja"
            tag="h2"
            cols="12"
            class="main__top__container__row__title"
          />
          <v-col
            cols="12"
            class="main__top__container__row__figure"
          >
            <v-img :src="face" :alt="name.ja" height="175px" width="175px" contain />
          </v-col>
          <v-col cols="12">
            <Sns />
          </v-col>
        </v-row>
      </v-container>
    </section>
    <section class="main__bottom">
      <v-container class="main__bottom__container">
        <v-row class="main__bottom__container__row">
          <v-col
            v-for="(item, index) in contents"
            :key="index"
            v-text="item"
            cols="12"
            tag="span"
          />
        </v-row>
      </v-container>
    </section>
  </main>
</template>

<script>
import Sns from '../components/Sns.vue'
import face from '@/assets/images/sugiyamatoshiki.svg'

export default {
  components: {
    Sns,
  },
  data() {
    return {
      face,
      name: {
        en: "Sugiyama Toshiki",
        ja: "スギヤマトシキ",
      },
      contents: [
        "　兵庫県出身、1990年生まれ",
        "　食品会社で3年間勤務の後、フィリピンセブ島でオフショア開発案件を担当しました。",
        "　WordPress、JavaScript(Vue.js、React)、PHP(Laravel)の学習も兼ねて、それらを用いた開発を行っています。",
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.main {
  &__top{
    background-color: $main-color;
    padding: $header-height+20px $side-space;
    height: 100vh;
    // height: 568px;
    text-align: center;
    color: $light-color;
    display: flex;
    align-items: center;
    &__container {
      &__row {
        &__title:first-child {
          font-size: 40px;
        }
        &__title:nth-child(2) {
          font-size: 20px;
        }
        &__figure {
          .v-image {
            border-radius: 50%;
            border: $light-color solid 1px;
            background-color: #fff;
            margin: 0 auto 30px;
            overflow: hidden;
          }
        }
      }
    }
  }
  &__bottom {
    padding: $header-height $side-space;
    background-color: #000;
    color: $light-color;
  }
}
</style>
