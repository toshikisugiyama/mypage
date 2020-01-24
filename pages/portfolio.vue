<template>
  <section class="portfolio">
    <h1 class="portfolio__title">portfolio</h1>
    <div class="portfolio__lists">
      <div class="portfolio__lists__item" v-for="work in works" :key="work.src">
        <a :href="work.url">
          <section class="portfolio__lists__item__contents">
              <h1 class="portfolio__lists__item__contents__title">{{ work.title }}</h1>
              <figure class="portfolio__lists__item__contents__figure">
                <img :src="work.src" :alt="work.title">
              </figure>
              <p class="portfolio__lists__item__contents__description">{{ work.description }}</p>
          </section>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import name_game from '@/assets/images/name_game.svg'
import count_down from '@/assets/images/count_down.svg'
export default {
  data() {
    return {
      works: [
        {title: '名前をつけて早く呼ぶゲーム', src: name_game, url: 'https://toshikisugiyama-images.netlify.com/', description: 'Adobe Illustrator による自作のイラストを用いたゲーム。もともと JavaScript で動かしていたが、学習のために React , Vueで作り直した。'},
        {title: '発表オープニング用カウントダウン', src: count_down, url: 'https://toshikisugiyama-ns-countdown.netlify.com/', description: '発表会の司会進行で、オープニングの際に開始までのカウントダウンをスクリーンに映したくて作った。学習のために React を使用。最初に時間を設定すると、その時間までのカウントダウンができる。設定時間になり、画面をクリックすると、発表の注意事項に移る。時間設定の際の初期設定は、17時（発表会が大抵17時開始だった為）。'},
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.portfolio {
  padding: $header-height 0;
  background-color: $light-color;
  color: $dark-color;
  &__title {
    text-align: center;
    padding: 0 $side-space;
    @include title;
  }
  &__lists {
    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    max-width: 1360px;
    margin: 0 auto;
    @media screen and (max-width: 680px) {
      justify-content: center;
    }
    &__item {
      width: 304px;
      margin: $side-space;
      &__contents {
        background-color: #fff;
        color: $dark-color;
        border-radius: 10px;
        padding: $side-space;
        &__title {
          margin-bottom: 10px;
        }
        &__figure {
          height: 149px;
          margin-bottom: 10px;
          transform: translateX($side-space*(-2));
        }
        &__description {
          transform: translateX($side-space);
        }
      }
    }
  }
}
</style>
