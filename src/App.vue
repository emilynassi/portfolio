<template>
  <div id="app">
    <NavBar headline="Emily Rosenkranz" />
  </div>
</template>

<script>
import NavBar from "./components/Navbar.vue";

export default {
  name: "App",
  components: {
    NavBar
  }
};
</script>

<style lang="scss">
@import "./assets/style.scss";
</style>
