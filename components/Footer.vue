<template>
  <footer class="footer">
    <div class="footer__sns"></div>
    <div class="footer__copyright">&#169;sugiyamatoshiki</div>
  </footer>
</template>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.footer {
  padding: $side-space;
  background-color: $dark-color;
  color: $light-color;
  &__sns {
    height: 30px;
    width: 100%;
    margin: $side-space;
  }
  &__copyright {
    text-align: center;
    margin: $side-space;
  }
}
</style>
