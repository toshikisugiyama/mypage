<template>
  <transition name="slide">
    <aside class="menu" v-if="activeMenu">
      <nav class="menu__nav">
        <ul class="menu__nav__lists">
          <li class="menu__nav__lists__item" v-for="menu in menus" :key="menu.title" @click="clickMenu">
            <n-link :to="menu.path">
              {{ menu.title }}
            </n-link>
          </li>
        </ul>
      </nav>
    </aside>
  </transition>
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
        { title: 'blog', path: '/blog', },
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
  animation: slide-in 0.8s;
}
.slide-leave-active {
  animation: slide-in 0.8s reverse;
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
  z-index: 9;
  @media screen and (min-width: 680px) {
    left: 50%;
  }
  &__nav {
    &__lists {
      list-style: none;
      padding: 0;
      &__item {
        height: $header-height*2.5;
        transition: background-color 0.3s;
        display: flex;
        flex-direction: column;
        justify-content: center;
        font-weight: bold;
        a {
          display: block;
          width: 100%;
          line-height: $header-height*2.5;
          padding: 0 $side-space;
          color: $dark-color;
        }
      }
      &__item:hover {
        background-color: $light-color;
      }
    }
  }
}
</style>
