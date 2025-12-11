<template>
  <!-- WRITING -->
  <section
    id="posts"
    class="pb-16 md:pb-32"
  >
    <h2 class="text-[clamp(2.5rem,7vw,5rem)] font-bold tracking-tight mb-8 md:mb-16">Posts</h2>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 md:gap-12">
      Coming Soon...
      <!-- <PostSummary
        v-for="post in posts"
        :key="post.title"
        :post="post"
      /> -->
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import PostSummary from './PostSummary.vue';
import type { Post } from './PostSummary.vue';
const posts = ref<Post[]>([
  {
    date: 'Nov 2025',
    tags: ['Homelab', 'Cloud'],
    title: 'Why I Still Run a Homelab in 2025',
    description:
      'Cloud is cheap. Managed services are easy. So why am I still racking servers in my closet?',
  },
  {
    date: 'Oct 2025',
    tags: ['Work', 'Observability'],
    title: "Teaching Observability to People Who Don't Care About Observability",
    description:
      'Notes on making infrastructure topics interesting to developers who just want to ship.',
  },
  {
    date: 'Sep 2025',
    tags: ['Homelab', 'Cloud'],
    title: 'The Synology Rabbit Hole',
    description: "I just wanted backups. Three weeks later I'm reading about SHR mirroring at 2am.",
  },
]);
</script>
