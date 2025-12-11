<script setup lang="ts">
import TheHeader from '../components/TheHeader.vue';
import TheProjects from '../components/TheProjects.vue';
import ThePosts from '../components/ThePosts.vue';
</script>

<template>
  <div class="max-w-[1400px] mx-auto px-6 md:px-12">
    <TheHeader />
    <main>
      <TheProjects />
      <ThePosts />
    </main>
  </div>
</template>
