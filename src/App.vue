<script setup lang="ts">
import { RouterView } from 'vue-router';
import ThemeToggle from './components/ThemeToggle.vue';
import TheFooter from './components/TheFooter.vue';
</script>

<template>
  <div class="wrapper bg-bg text-text-primary font-sans antialiased transition-colors duration-300">
    <ThemeToggle />
    <RouterView />
    <TheFooter />
  </div>
</template>
