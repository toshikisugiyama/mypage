<template lang="pug">
  transition(name="fade")
    .layer(@click="clickMenu" v-if="activeMenu")
</template>

<script>
export default {
  props: {
    activeMenu: {
      type: Boolean,
      required: true,
    }
  },
  methods: {
    clickMenu: function() {
      this.$emit('clickMenu', !this.activeMenu)
    },
  },
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variable.scss";
$layer-opacity: 0.5;
.fade-enter-active {
  animation: fade-in $animation-time ease 0s;
}
.fade-leave-active {
  animation: fade-in $animation-time ease 0s reverse;
}
@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: $layer-opacity;
  }
}
.layer {
  background-color: $dark-color;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  opacity: $layer-opacity;
  z-index: 10;
  cursor: pointer;
  @media screen and (max-width: $tab) {
    display: none;
  }
}
</style>
