<template>
<main class="portfolio">
  <v-container class="portfolio__content" tag="section" >
    <v-row class="portfolio__content__row">
      <v-col v-text="title.toUpperCase()" tag="h1" cols="12" class="portfolio__content__row__title" />
    </v-row>
    <v-row class="portfolio__content__wrapper">
      <v-col v-for="work in works" :key="work.src" class="portfolio__content__wrapper__item" cols="12" md="4">
        <v-card @click="toPage(work.url)">
          <v-card-title v-text="work.title" />
          <v-img :src="work.src" :alt="work.title" />
          <v-card-text v-text="work.description" />
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</main>
</template>

<script>
import name_game from '@/assets/images/name_game.svg'
import count_down from '@/assets/images/count_down.svg'
import todo_app from '@/assets/images/todo_app.svg'
export default {
  data() {
    return {
      title: 'portfolio',
      works: [
        {title: '名前をつけて早く呼ぶゲーム', src: name_game, url: 'https://toshikisugiyama-images.netlify.com/', description: 'Adobe Illustrator による自作のイラストを用いたゲーム。もともと JavaScript で動かしていたが、学習のために React , Vueで作り直した。'},
        {title: '発表オープニング用カウントダウン', src: count_down, url: 'https://toshikisugiyama-ns-countdown.netlify.com/', description: '発表会の司会進行で、オープニングの際に開始までのカウントダウンをスクリーンに映したくて作った。学習のために React を使用。最初に時間を設定すると、その時間までのカウントダウンができる。設定時間になり、画面をクリックすると、発表の注意事項に移る。時間設定の際の初期設定は、17時（発表会が大抵17時開始だった為）。'},
        {title: 'ToDoアプリ', src: todo_app, url: 'http://obscure-falls-29065.herokuapp.com/', description: 'LaravelとVue.jsで作ったTodoアプリ。ログインログアウト機能、フォルダ追加機能、タスク追加、編集、削除機能を実装。'},
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
.portfolio {
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
          .v-image {
            transform: translateX(-3%);
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
