<template lang="pug">
  main.main
    section.main__top
      v-container.main__top__container
        v-row.main__top__container__row
          v-col.main__top__container__row__title(v-text="name.en" tag="h1" cols="12")
          v-col.main__top__container__row__title(v-text="name.ja" tag="h2" cols="12")
          v-col.main__top__container__row__figure(cols="12")
            v-img(:src="face" :alt="name.ja" height="175px" width="175px" contain)
          v-col(cols="12")
            Sns
    section.main__bottom
      v-container.main__bottom__container
        v-row.main__bottom__container__row
          v-col(v-for="(item, index) in contents" :key="index" v-text="item" cols="12" tag="p")
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
        "1990年生まれ、兵庫県 出身",
        "2019年4月〜2019年9月　NexSeed.Incでインターン(エンジニアクラス補佐・オフショア業務)",
        "2018年7月〜現在　WordPressによるホームページ作成",
        "2018年4月〜2018年6月　フィリピン・セブ島のNexSeed.Incで留学(英語・Web)",
        "2015年4月〜2018年3月　マルカン酢株式会社",
        "2015年3月　関西学院大学大学院 理工学研究科 修了",
        "2013年3月　関西学院大学 理工学部 生命科学科 卒業",
        "大学、大学院で植物プランクトンの研究をしました。卒業後、微生物を用いて作る調味料である、お酢を作る食品会社で製造業に従事しました。その中で、ITで製造過程を管理するシステムが導入されつつあり、自分にはITの知識が足りないということと、これからはもっとそのような知識が必須になってくると感じました。また、海外にも興味があったため、退職を決意しフィリピンに渡り、英語とプログラミングを学びました。その後、WordPressでのホームページ制作などの案件を受けています。さらに、再度フィリピンに渡り、スクールにてエンジニアクラスの補佐やオフショアでのWeb開発のコミュニケーター業務を行いました。現在はホームページ制作を続けながらフロントエンドなどの新しい技術を身につけるため学習も続けています。"
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
    padding: $header-height 0;
    background-color: #000;
    color: $light-color;
  }
}
</style>
