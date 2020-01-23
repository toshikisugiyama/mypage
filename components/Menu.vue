<template>
  <transition name="slide">
    <aside class="menu" v-if="activeMenu">
      <nav>
        <ul>
          <li>メニュー</li>
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
}
</script>

<style lang="scss" scoped>
.slide-enter-active {
  animation: slide-in 0.3s;
}
.slide-leave-active {
  animation: slide-in 0.3s reverse;
}
@keyframes slide-in {
  from {
    transform: translateX(1000px)
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
}
</style>
