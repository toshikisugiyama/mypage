<template>
  <section class="contact">
    <h1 class="contact__title">contact</h1>
  </section>
</template>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.contact{
  padding: $header-height $side-space;
  background-color: $main-color;
  height: 100vh;
  color: $light-color;
  &__title {
    text-align: center;
    padding: 0 $side-space;
    @include title;
  }
}
</style>

