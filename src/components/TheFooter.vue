<template>
  <!-- FOOTER -->
  <footer class="border-t border-border mt-8 transition-colors duration-300">
    <div class="max-w-[1400px] mx-auto px-6 md:px-12 py-12">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
        <span class="text-sm text-text-muted">Built with too much coffee.</span>
        <div class="flex gap-6">
          <a
            v-for="link in links"
            :key="link.label"
            :href="link.href"
            class="px-2.5 py-1 text-sm font-medium rounded transition-colors"
            :class="[link.color, link.color ? 'text-black' : 'text-black dark:text-white']"
            :target="link.target || '_self'"
            >{{ link.label }}</a
          >
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import type { Link } from './TheHeader.vue';
const links = ref<Link[]>([
  {
    label: 'GitHub',
    href: 'https://github.com/emilynassi',
    color: 'bg-tag-yellow',
    target: '_blank',
  },
  {
    label: 'LinkedIn',
    href: 'https://www.linkedin.com/in/emilynassi/',
    color: 'bg-tag-pink',
    target: '_blank',
  },
  {
    label: 'Email',
    href: 'mailto:emily.nassi1@gmail.com',
    color: 'bg-tag-blue',
    target: '_self',
  },
]);
</script>
