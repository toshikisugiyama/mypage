<template lang="pug">
  .sns
    figure.sns__item(v-for="sns in snsAccounts" :key="sns.name")
      a(:href="sns.url")
        img(:src="sns.src" :alt="sns.name" height="32px")
</template>

<script>
import github from '@/assets/images/github.svg'
import twitter from '@/assets/images/twitter.svg'
import facebook from '@/assets/images/facebook.svg'
import instagram from '@/assets/images/instagram.svg'
import qiita from '@/assets/images/qiita.svg'
export default {
  data() {
    return {
      snsAccounts: [
        {name: 'github', src: github, url: 'https://github.com/toshikisugiyama',},
        {name: 'qiita', src: qiita, url: 'https://qiita.com/toshikisugiyama',},
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
.sns {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 200px;
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
</style>
