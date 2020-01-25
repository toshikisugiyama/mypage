<template>
  <div>
    <main class="main">
      <section class="main__top">
        <h1 class="main__top__title">Sugiyama Toshiki</h1>
        <h2 class="main__top__title">スギヤマトシキ</h2>
        <figure class="main__top__figure">
          <img :src="face" alt="sugiyamatoshiki" height="180px">
        </figure>
        <div class="main__top__sns">
          <figure
            class="main__top__sns__item"
            v-for="sns in snsAccounts"
            :key="sns.name"
          >
            <a :href="sns.url">
              <img :src="sns.src" :alt="sns.name" height="32px">
            </a>
          </figure>
        </div>
      </section>
      <section class="main__bottom">
        <h1 class="main__bottom__title">自己紹介</h1>
        <p>　兵庫県出身、1990年生まれ</p>
        <p>　学生時代は、3年間藻類を研究しました。</p>
        <p>　食酢の製造会社で3年間勤務の後、フィリピンセブ島のスクールで英語とプログラミングを勉強し、翌年には再びセブ島に戻り、オフショア開発案件を担当しました。</p>
        <p>　現在WordPressの案件を受けていますが、Vue.js、ReactなどのJavaScriptフレームワークやPHPフレームワークのLaravelの学習を兼ねて、それらを用いた開発を行っています。</p>
      </section>
    </main>
    <Footer />
  </div>
</template>

<script>
import Footer from '../components/Footer.vue'
import face from '@/assets/images/sugiyamatoshiki.svg'
import github from '@/assets/images/github.svg'
import twitter from '@/assets/images/twitter.svg'
import facebook from '@/assets/images/facebook.svg'
import instagram from '@/assets/images/instagram.svg'

export default {
  components: {
    Footer,
  },
  data() {
    return {
      face,
      snsAccounts: [
        {name: 'github', src: github, url: 'https://github.com/toshikisugiyama',},
        {name: 'twitter', src: twitter, url: 'https://twitter.com/llwz886q',},
        {name: 'facebook', src: facebook, url: 'https://www.facebook.com/toshiki.sugiyama.31',},
        {name: 'instagram', src: instagram, url: 'https://www.instagram.com/axa81468',},
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.main {
  &__top{
    padding: $header-height+20px $side-space;
    background-color: $main-color;
    height: 568px;
    text-align: center;
    color: $light-color;
    &__title:first-child {
      margin: 10px auto;
      font-size: 40px;
    }
    &__title:nth-child(2) {
      margin: 10px auto 40px;
      font-size: 20px;
    }
    &__figure {
      width: 175px;
      height: 175px;
      border-radius: 50%;
      border: $light-color solid 1px;
      background-color: #fff;
      margin: 0 auto 40px;
      overflow: hidden;
      img {
        object-fit: contain;
      }
    }
    &__sns {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 175px;
      margin: 0 auto;
      &__item {
        margin: 0;
        height: 30px;
        width: 30px;
        overflow: hidden;
        border: $light-color solid 1px;
        border-radius: 5px;
        a {
          height: 100%;
          width: 100%;
          display: flex;
          justify-content: center;
          align-items: center;
          background-color: $light-color;
          img {
            object-fit: cover;
          }
        }
      }
    }
  }
  &__bottom {
    padding: $header-height $side-space $header-height*2;
    background-color: #000;
    color: $light-color;
    &__title {
      text-align: center;
      @include title;
    }
    p {
      margin: 0 0 $side-space/2 0;
    }
  }
}
</style>
