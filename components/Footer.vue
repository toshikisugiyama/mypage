<template lang="pug">
  footer.footer
    Sns
    .footer__copyright &#169;sugiyamatoshiki
</template>

<script>
import Sns from '../components/Sns.vue'
export default {
  components: {
    Sns,
  }
}

</script>
<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.footer {
  padding: $header-height $side-space $side-space;
  background-color: #000;
  color: $light-color;
  &__copyright {
    text-align: center;
    margin: $side-space;
  }
}
</style>
