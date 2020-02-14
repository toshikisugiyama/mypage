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
            <v-img :src="face" :alt="name.ja" height="180px" contain />
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
        "　学生時代は、3年間藻類を研究しました。",
        "　食酢の製造会社で3年間勤務の後、フィリピンセブ島のスクールで英語とプログラミングを学び、翌年には再びセブ島に戻り、オフショア開発案件を担当しました。",
        "　現在WordPressの案件を受けていますが、Vue.js、ReactなどのJavaScriptフレームワークやPHPフレームワークのLaravelの学習を兼ねて、それらを用いた開発を行っています。",
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
    height: 568px;
    text-align: center;
    color: $light-color;
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
            width: 175px;
            height: 175px;
            border-radius: 50%;
            border: $light-color solid 1px;
            background-color: #fff;
            margin: 0 auto 40px;
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
