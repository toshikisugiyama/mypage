<template lang="pug">
  transition(name="slide")
    aside.menu(v-if="activeMenu")
      nav.menu__nav
        ul.menu__nav__lists
          li.menu__nav__lists__item(v-for="menu in menus" :key="menu.title" @click="clickMenu")
            n-link(:to="menu.path") {{ menu.title.toUpperCase() }}
</template>

<script>
export default {
  props: {
    activeMenu: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      menus: [
        { title: 'top', path: '/', },
        { title: 'portfolio', path: '/portfolio', },
        { title: 'illustrator', path: '/illustrator', },
        { title: 'contact', path: '/contact', },
      ],
    }
  },
  methods: {
    clickMenu: function() {
      this.$emit('clickMenu', !this.activeMenu)
    }
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.slide-enter-active {
  animation: slide-in $animation-time;
}
.slide-leave-active {
  animation: slide-in $animation-time reverse;
}
@keyframes slide-in {
  from {
    transform: translateX(3000px)
  }
  to {
    transform: translateX(0)
  }
}
.menu {
  background-color: #fff;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  padding: $header-height 0;
  z-index: 11;
  @media screen and (min-width: $tab) {
    left: 50%;
  }
  &__nav {
    &__lists {
      list-style: none;
      padding: 0;
      &__item {
        height: $header-height*2.5;
        transition: background-color $animation-time;
        display: flex;
        flex-direction: column;
        justify-content: center;
        font-weight: bold;
        a {
          display: block;
          width: 100%;
          line-height: $header-height*2.5;
          color: $dark-color;
          padding: 0 $side-space;
        }
      }
      &__item:hover {
        background-color: $light-color;
      }
    }
  }
}
</style>
