<template>
  <!-- PROJECTS -->
  <section
    id="projects"
    class="pb-16 md:pb-32"
  >
    <h2 class="text-[clamp(2.5rem,7vw,5rem)] font-bold tracking-tight mb-8 md:mb-16">
      Featured Projects
    </h2>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 md:gap-12">
      <ProjectBlock
        v-for="project in projects"
        :key="project.title"
        :project="project"
      />
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import ProjectBlock from './ProjectBlock.vue';
import type { Project } from './ProjectBlock.vue';
const projects = ref<Project[]>([
  {
    year: 2025,
    tags: ['Vue', 'TypeScript'],
    title: 'NHL Color Accessibility Checker',
    link: 'https://nhl-color-checker.netlify.app/',
    description:
      'Visualizes how NHL team colors appear under different types of color blindness, with an interactive hockey rink display. Inspired by this photo <a class="underline" href="https://www.instagram.com/p/DRJIFt6ke2-/" target="_blank">here</a>.',
  },
  {
    year: 2025,
    tags: ['Next.js', 'TypeScript'],
    title: 'NHL Time on Ice tracker',
    link: 'https://toi-tracker.vercel.app/',
    description: 'Tracks the time on ice for NHL players and teams.',
  },
  {
    year: 2024,
    tags: ['Node.js', 'JavaScript'],
    title: 'Discord Prediction Bot',
    link: 'https://github.com/emilynassi/pickem-command',
    description:
      'Handles over/underpredictions for gaming communities with vote reconciliation and persistent state across sessions.',
  },
]);
</script>
