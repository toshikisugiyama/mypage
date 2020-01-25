<template>
  <section class="blog">
    <h1 class="blog__title">blog</h1>
  </section>
</template>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.blog {
  padding: $header-height $side-space;
  background-color: $main-color;
  color: $light-color;
  height: 100vh;
  &__title {
    text-align: center;
    padding: 0 $side-space;
    @include title;
  }
}
</style>
