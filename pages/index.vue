<template>
  <main class="main">
    <section class="main__top">
      <h1 class="main__top__title">Sugiyama Toshiki</h1>
      <h2 class="main__top__title">スギヤマトシキ</h2>
      <figure class="main__top__figure">
        <img src="../assets/sugiyamatoshiki.svg" alt="sugiyamatoshiki" height="180px">
      </figure>
      <div class="main__top__sns">
        <figure class="main__top__sns__item">
          <a href="https://github.com/toshikisugiyama">
            <img src="../assets/github.svg" alt="github" height="30px">
          </a>
        </figure>
        <figure class="main__top__sns__item">
          <a href="https://twitter.com/llwz886q">
            <img src="../assets/twitter.svg" alt="twitter" height="30px">
          </a>
        </figure>
        <figure class="main__top__sns__item">
          <a href="https://www.facebook.com/toshiki.sugiyama.31">
            <img src="../assets/facebook.svg" alt="facebook" height="30px">
          </a>
        </figure>
        <figure class="main__top__sns__item">
          <a href="https://www.instagram.com/axa81468">
            <img src="../assets/instagram.svg" alt="instagram" height="30px">
          </a>
        </figure>
      </div>
    </section>
    <section class="main__bottom">
      <h1>自己紹介</h1>
      <p>　兵庫県出身、1990年生まれ</p>
      <p>　学生時代は、3年間藻類を研究しました。</p>
      <p>　食酢の製造会社で3年間勤務の後、フィリピンセブ島のスクールで英語とプログラミングを勉強し、翌年には再びセブ島に戻り、オフショア開発案件を担当しました。</p>
      <p>　現在WordPressの案件を受けていますが、Vue.js、ReactなどのJavaScriptフレームワークやPHPフレームワークのLaravelの学習を兼ねて、それらを用いた開発を行っています。</p>
    </section>
  </main>
</template>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.main {
  &__top{
    padding: $header-height+20px $side-space;
    background-color: #868282;
    height: 568px;
    text-align: center;
    &__title {
      color: #fff;
    }
    h1 {
      margin: 10px auto;
      font-size: 40px;
    }
    h2 {
      margin: 10px auto 40px;
      font-size: 20px;
    }
    &__figure {
      width: 175px;
      height: 175px;
      border-radius: 50%;
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
        img {
          object-fit: contain;
        }
      }
    }
  }
  &__bottom {
    padding: 18px;
  }
}
</style>
