<template>
  <div id="app">
    <NavBar headline="Emily Rosenkranz" />
    <Main />
    <Footer />
  </div>
</template>

<script>
import NavBar from './components/Navbar.vue'
import Main from './components/Main.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Main,
    Footer
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Heebo:wght@400;500;600;700;800;900&display=swap');
@import './assets/style.scss';
</style>
