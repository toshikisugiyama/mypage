<template>
  <header class="header">
    <div
      class="header__menu"
      :class="{'header__menu_open': activeMenu}"
      @click="clickMenu"
    >
      <div class="header__menu__bar"></div>
      <div class="header__menu__bar"></div>
      <div class="header__menu__bar"></div>
    </div>
  </header>
</template>

<script>
export default {
  props: {
    activeMenu: {
      type: Boolean,
      required: true,
    },
  },
  methods: {
    clickMenu: function() {
      this.$emit('clickMenu', !this.activeMenu)
    },
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.header {
  height: $header-height;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 0 18px;
  z-index: 20;
  &__menu {
    height: 20px;
    width: 30px;
    cursor: pointer;
    &__bar {
      height: 2px;
      width: 100%;
      margin-bottom: 5px;
      background-color: $light-color;
      filter: drop-shadow(1px 1px 1px $dark-color);
      transition: all $animation-time ease-out;
    }
    &_bar:last-child {
      margin-bottom: 0;
    }
  }
  &__menu_open {
    position: relative;
    .header__menu__bar {
      background-color: $dark-color;
      filter: none;
    }
    .header__menu__bar:first-child,
    .header__menu__bar:nth-child(2) {
      position: absolute;
      top: 50%;
      right: 0;
      margin: 0;
    }
    .header__menu__bar:first-child {
      transform: rotate(-45deg);
    }
    .header__menu__bar:nth-child(2) {
      transform: rotate(45deg);
    }
    .header__menu__bar:last-child {
      display: none;
    }
  }
}
</style>
