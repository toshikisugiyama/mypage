<template>
  <div>
    <Header :activeMenu="activeMenu" @clickMenu="activeMenu=$event" />
    <Layer :activeMenu="activeMenu" @clickMenu="activeMenu=$event" />
    <Menu :activeMenu="activeMenu" @clickMenu="activeMenu=$event" />
    <nuxt />
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Layer from '@/components/Layer.vue'
import Menu from '@/components/Menu.vue'
import Footer from '../components/Footer.vue'
export default {
  components: {
    Header,
    Layer,
    Menu,
    Footer,
  },
  data() {
    return {
      activeMenu: false,
    }
  }
}
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

a {
  text-decoration: none;
}
</style>
